---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 116e007cc28a91e3c97fd980cc27461932390b7c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227033"
---
# Start-Job

## Краткий обзор
Запускает фоновое задание PowerShell.

## SYNTAX

### ComputerName (по умолчанию)

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### DefinitionName

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [<CommonParameters>]
```

### филепаскомпутернаме

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### литералфилепаскомпутернаме

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## DESCRIPTION

`Start-Job`Командлет запускает фоновое задание PowerShell на локальном компьютере.

Фоновое задание PowerShell выполняет команду без взаимодействия с текущим сеансом. При запуске фонового задания объект задания возвращается немедленно, даже если для завершения задания требуется дополнительное время. Пока задание выполняется, можно продолжать работу с данным сеансом.

Объект задания содержит полезные сведения о задании, но не содержит результатов задания.
По завершении задания используйте `Receive-Job` командлет для получения результатов задания. Дополнительные сведения о фоновых заданиях см. в разделе [about_Jobs](./About/about_Jobs.md).

Чтобы запустить фоновое задание на удаленном компьютере, используйте параметр **AsJob** , доступный во многих командлетах, или используйте `Invoke-Command` командлет для выполнения `Start-Job` команды на удаленном компьютере. Дополнительные сведения см. в разделе [about_Remote_Jobs](./About/about_Remote_Jobs.md).

Начиная с версии PowerShell 3,0, `Start-Job` можно запускать экземпляры пользовательских типов заданий, например запланированные задания. Сведения об использовании `Start-Job` для запуска заданий с пользовательскими типами см. в справочных документах по функциям типа задания.

Рабочий каталог по умолчанию для заданий является жестко закодированным. По умолчанию Windows имеет значение `$HOME\Documents` , а в Linux или macOS значение по умолчанию — `$HOME` . Код скрипта, выполняемый в фоновом задании, должен управлять рабочим каталогом по мере необходимости.

## Примеры

### Пример 1. Запуск фонового задания

В этом примере запускается фоновое задание, выполняемое на локальном компьютере.

```powershell
Start-Job -ScriptBlock { Get-Process -Name powershell }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name powershell
```

`Start-Job` использует параметр **ScriptBlock** для выполнения в `Get-Process` качестве фонового задания. Параметр **Name** указывает на поиск процессов PowerShell `powershell` . Отображаются сведения о задании, и PowerShell возвращается в командную строку, пока задание выполняется в фоновом режиме.

Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет. Например, `Receive-Job -Id 1`.

### Пример 2. Запуск задания с помощью Invoke-Command

В этом примере выполняется задание на нескольких компьютерах. Задание хранится в переменной и выполняется с помощью имени переменной в командной строке PowerShell.

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

Задание, которое использует, `Invoke-Command` создается и сохраняется в `$jobWRM` переменной. `Invoke-Command` использует параметр **ComputerName** для указания компьютеров, на которых выполняется задание. `Get-Content` Возвращает имена серверов из `C:\Servers.txt` файла.

Параметр **ScriptBlock** указывает команду, которая `Get-Service` Получает службу **WinRM** . Параметр **JobName** указывает понятное имя для задания, **WinRM**. Параметр **ThrottleLimit** ограничивает количество одновременных команд до 16. Параметр **AsJob** запускает фоновое задание, которое выполняет команду на серверах.

### Пример 3. Получение сведений о задании

Этот пример получает сведения о задании и отображает результаты завершенного задания, которое было запущено на локальном компьютере.

```powershell
$j = Start-Job -ScriptBlock { Get-WinEvent -Log System } -Credential Domain01\User01
$j | Select-Object -Property *
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-WinEvent -Log System
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : 27ce3fd9-40ed-488a-99e5-679cd91b9dd3
Id            : 18
Name          : Job18
ChildJobs     : {Job19}
PSBeginTime   : 8/8/2019 14:41:57
PSEndTime     : 8/8/2019 14:42:07
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

`Start-Job` использует параметр **ScriptBlock** для выполнения команды, указывающей `Get-WinEvent` на получение **системного** журнала. Параметр **Credential** указывает учетную запись пользователя домена с разрешением на запуск задания на компьютере. Объект задания хранится в `$j` переменной.

Объект в `$j` переменной отправляется по конвейеру в `Select-Object` . Параметр **Property** задает звездочку ( `*` ) для вывода свойств объекта задания.

### Пример 4. Запуск скрипта как фонового задания

В этом примере сценарий на локальном компьютере выполняется как фоновое задание.

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

`Start-Job` использует параметр **FilePath** для указания файла скрипта, хранящегося на локальном компьютере.

### Пример 5. получение процесса с помощью фонового задания

В этом примере для получения указанного процесса по имени используется фоновое задание.

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

`Start-Job` использует параметр **Name** для указания понятного имени задания **пшеллжоб**. Параметр **ScriptBlock** указывает `Get-Process` на получение процессов с именем **PowerShell**.

### Пример 6. получение и сохранение данных с помощью фонового задания

В этом примере запускается задание, которое собирает большой объем данных о карте и сохраняет их в `.tif` файле.

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif } -RunAs32
```

`Start-Job` использует параметр **Name** для указания понятного имени задания **жетмаппингфилес**. Параметр **инитиализатионскрипт** выполняет блок скрипта, который импортирует модуль **мапфунктионс** . Параметр **ScriptBlock** выполняется `Get-Map` и `Set-Content` сохраняет данные в расположении, указанном параметром **path** . Параметр **RunAs32** запускает процесс как 32-разрядный, даже в 64-разрядной операционной системе.

### Пример 7. передача входных данных в фоновое задание

В этом примере `$input` Автоматическая переменная используется для обработки входного объекта. Используйте `Receive-Job` для просмотра выходных данных задания.

```powershell
Start-Job -ScriptBlock { Get-Content $input } -InputObject "C:\Servers.txt"
Receive-Job -Name Job45 -Keep
```

```Output
Server01
Server02
Server03
Server04
```

`Start-Job` использует параметр **ScriptBlock** для выполнения `Get-Content` с `$input` автоматической переменной. `$input`Переменная получает объекты из параметра **InputObject** . `Receive-Job` использует параметр **Name** для указания задания и вывода результатов. Параметр **сохранить** сохраняет выходные данные задания, чтобы их можно было снова просмотреть во время сеанса PowerShell.

### Пример 8. Использование параметра ArgumentList для указания массива

В этом примере используется параметр **ArgumentList** для указания массива аргументов. Массив представляет собой разделенный запятыми список имен процессов.

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

`Start-Job`Командлет использует параметр **ScriptBlock** для выполнения команды. `Get-Process` Задает автоматическую переменную с помощью параметра **Name** `$args` . Параметр **ArgumentList** передает массив имен процессов в `$args` . Имена процессов PowerShell, pwsh и Notepad — это процессы, выполняемые на локальном компьютере.

Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет. Например, `Receive-Job -Id 1`.

## PARAMETERS

### -ArgumentList

Задает массив аргументов или значений параметров для скрипта, заданного параметром **FilePath** , или команды, указанной с помощью параметра **ScriptBlock** .

Аргументы должны передаваться в **ArgumentList** как аргумент массива с одним измерением. Например, список с разделителями-запятыми. Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication

Указывает механизм, используемый для проверки подлинности учетных данных пользователя.

Для этого параметра допустимы следующие значения:

- По умолчанию
- Базовый
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential

Значение по умолчанию — Default.

Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. Если параметр **Credential** не указан, команда использует учетные данные текущего пользователя.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionName

Указывает имя определения задания, запускаемого этим командлетом. Используйте этот параметр для запуска заданий настраиваемых типов, имеющих имя определения, например запланированных заданий.

При использовании `Start-Job` для запуска экземпляра запланированного задания задание запускается немедленно, независимо от триггеров задания или параметров задания. Результирующий экземпляр задания — это запланированное задание, но оно не сохраняется на диск, например запуск запланированных заданий. Параметр **ArgumentList** аргумента нельзя использовать `Start-Job` для предоставления значений для параметров скриптов, выполняемых в запланированном задании. Дополнительные сведения см. в разделе [about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md).

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionPath

Указывает путь определения задания, запускаемого этим командлетом. Введите путь определения. Объединение значений параметров **DefinitionPath** и **DefinitionName** является полным путем к определению задания. Используйте этот параметр для запуска заданий настраиваемых типов, которые имеют путь к определению, например запланированных заданий.

Для запланированных заданий значение параметра **DefinitionPath** равно `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает локальный скрипт, который `Start-Job` выполняется как фоновое задание. Введите путь и имя файла скрипта или используйте конвейер для отправки пути скрипта в `Start-Job` . Сценарий должен находиться на локальном компьютере или в папке, к которой может получить доступ локальный компьютер.

При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта и запускает блок скрипта в качестве фонового задания.

```yaml
Type: System.String
Parameter Sets: FilePathComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инитиализатионскрипт

Указывает команды, выполняемые перед запуском задания. Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).

Используйте этот параметр для подготовки сеанса, в рамках которого выполняется задание. Например, его можно использовать для добавления в сеанс функций, оснасток и модулей.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает входные данные команды. Введите переменную, содержащую объекты, либо введите команду или выражение для создания объектов.

В значении параметра **ScriptBlock** используйте `$input` автоматическую переменную для представления входных объектов.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Задает локальный скрипт, выполняемый этим командлетом в качестве фонового задания. Введите путь к скрипту на локальном компьютере.

`Start-Job` использует значение параметра **LiteralPath** точно так же, как оно типизировано. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает понятное имя нового задания. С помощью имени можно указать задание для других командлетов задания, например `Stop-Job` командлета.

Понятное имя по умолчанию — `Job#` , где `#` — порядковый номер, увеличивающийся для каждого задания.

```yaml
Type: System.String
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSVersion

Указывает версию. `Start-Job` запускает задание с версией PowerShell. Допустимые значения для этого параметра: `2.0` и `3.0` .

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Version
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAs32

Указывает, что `Start-Job` запускает задание в 32-разрядном процессе. **RunAs32** принудительно запускает задание в 32-разрядном процессе даже в 64-разрядной операционной системе.

В 64-разрядных версиях Windows 7 и Windows Server 2008 R2, если `Start-Job` команда содержит параметр **RunAs32** , нельзя использовать параметр **Credential** для указания учетных данных другого пользователя.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Указывает команды, которые нужно выполнить в фоновом задании. Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ). Используйте `$input` автоматическую переменную для доступа к значению параметра **InputObject** . Этот параметр обязателен.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Указывает пользовательский тип для заданий, запускаемых `Start-Job` . Введите имя настраиваемого типа задания, например PSScheduledJob для запланированных заданий или PSWorkflowJob для заданий рабочих процессов. Этот параметр не является допустимым для стандартных фоновых заданий.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Конвейер можно использовать для отправки объекта со свойством **Name** в параметр **Name** . Например, можно выполнить конвейер объекта **FileInfo** из `Get-ChildItem` в `Start-Job` .

## Выходные данные

### System. Management. Automation. Псремотингжоб

`Start-Job` Возвращает объект **псремотингжоб** , представляющий запущенное задание.

## ПРИМЕЧАНИЯ

Для запуска в фоновом режиме `Start-Job` выполняется в собственном сеансе в текущем сеансе. При использовании `Invoke-Command` командлета для выполнения `Start-Job` команды в сеансе на удаленном компьютере `Start-Job` выполняется в сеансе удаленного сеанса.

## Связанные ссылки

[about_Arrays](./about/about_arrays.md)

[about_Automatic_Variables](./about/about_automatic_variables.md)

[about_Jobs](./About/about_Jobs.md)

[about_Job_Details](./About/about_Job_Details.md)

[about_Remote_Jobs](./About/about_Remote_Jobs.md)

[Get-Job.](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
