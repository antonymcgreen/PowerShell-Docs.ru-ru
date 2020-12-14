---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: 1f06d1e7114a84ea89097167b188ded605f81aa0
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564543"
---
# Get-Module

## Краткий обзор
Выводит список модулей, импортированных в текущем сеансе или импортируемых из PSModulePath.

## SYNTAX

### Загружено (по умолчанию)

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### Доступно

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] [<CommonParameters>]
```

### PsSession

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### CimSession

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-SkipEditionCheck] [-Refresh] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

## DESCRIPTION

`Get-Module`Командлет перечисляет модули PowerShell, которые были импортированы или могут быть импортированы, в сеанс PowerShell. Без параметров `Get-Module` возвращает модули, которые были импортированы в текущий сеанс. Параметр **ListAvailable** используется для перечисления модулей, доступных для импорта из путей, указанных в переменной среды PSModulePath ( `$env:PSModulePath` ).

Объект модуля, который `Get-Module` возвращает, содержит ценные сведения о модуле. Можно также передать объекты модуля в другие командлеты, такие как `Import-Module` `Remove-Module` командлеты и.

`Get-Module` Выводит список модулей, но не импортирует их. Начиная с Windows PowerShell 3,0 модули автоматически импортируются при использовании команды в модуле, но `Get-Module` команда не запускает автоматический импорт. Вы также можете импортировать модули в сеанс с помощью `Import-Module` командлета.

Начиная с Windows PowerShell 3,0, вы можете получить и импортировать модули из удаленных сеансов в локальный сеанс. Эта стратегия использует функцию неявного удаленного взаимодействия PowerShell и эквивалентна использованию `Import-PSSession` командлета. При использовании команд в модулях, импортированных из другого сеанса, команды выполняются неявно в удаленном сеансе. Эта функция позволяет управлять удаленным компьютером из локального сеанса.

Кроме того, начиная с Windows PowerShell 3,0, вы можете использовать `Get-Module` и `Import-Module` для получения и импорта модулей модель CIM (CIM). Модули CIM определяют командлеты в файлах XML определения командлетов (CDXML). Эта функция позволяет использовать командлеты, реализованные в неуправляемых сборках кода, таких как написанные на C++.

Неявное удаленное взаимодействие можно использовать для управления удаленными компьютерами, на которых включено удаленное взаимодействие PowerShell.
Создайте сеанс **PSSession** на удаленном компьютере, а затем используйте параметр **PSSession** , `Get-Module` чтобы получить модули PowerShell в удаленном сеансе. При импорте модуля из удаленного сеанса импортированные команды выполняются в сеансе на удаленном компьютере.

Аналогичную стратегию можно использовать для управления компьютерами, на которых не включено удаленное взаимодействие PowerShell.
К ним относятся компьютеры, на которых не установлена операционная система Windows, а также компьютеры с PowerShell, для которых не включено удаленное взаимодействие PowerShell.

Начните с создания сеанса CIM на удаленном компьютере. Сеанс CIM — это подключение к инструментарий управления Windows (WMI) (WMI) на удаленном компьютере. Затем используйте параметр **CIMSession** параметра, `Get-Module` чтобы получить модули CIM из сеанса CIM. При импорте модуля CIM с помощью `Import-Module` командлета и последующем выполнении импортированных команд команды выполняются неявно на удаленном компьютере. С помощью этой стратегии, предполагающей использование инструментария WMI и модели CIM, можно управлять удаленным компьютером.

## Примеры

### Пример 1. получение модулей, импортированных в текущий сеанс

```powershell
Get-Module
```

Эта команда возвращает модули, которые были импортированы в текущий сеанс.

### Пример 2. Получение установленных модулей и доступных модулей

```powershell
Get-Module -ListAvailable
```

Эта команда возвращает модули, которые установлены на компьютере и могут быть импортированы в текущий сеанс.

`Get-Module` ищет доступные модули по пути, указанному в переменной среды **$env:P смодулепас** . Подробнее о переменной среды **PSModulePath**, см. в разделах [about_Modules](About/about_Modules.md) и [about_Environment_Variables](About/about_Environment_Variables.md).

### Пример 3. получение всех экспортированных файлов

```powershell
Get-Module -ListAvailable -All
```

Эта команда возвращает все экспортированные файлы для всех доступных модулей.

### Пример 4. Получение модуля по его полному имени

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

Эта команда получает модуль **Microsoft. PowerShell. Management** , указывая полное имя модуля с помощью параметра **FullyQualifiedName** . Затем команда передает результаты в `Format-Table` командлет, чтобы отформатировать результаты в виде таблицы с **именами** и **версиями** в качестве заголовков столбцов.

### Пример 5. получение свойств модуля

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

Эта команда возвращает свойства объекта **PSModuleInfo** , который `Get-Module` возвращает. Для каждого файла модуля имеется один объект.

С помощью свойств можно форматировать и фильтровать объекты модулей. Дополнительные сведения о свойствах см. в разделе [Свойства PSModuleInfo](/dotnet/api/system.management.automation.psmoduleinfo).

Выходные данные включают новые свойства, такие как **Author** и **CompanyName**, которые появились в Windows PowerShell 3,0.

### Пример 6. Группировка всех модулей по имени

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

Эта команда возвращает все файлы модулей, импортированные и доступные, а затем группирует их по имени модуля. Это позволяет увидеть, какие файлы модулей экспортирует каждый сценарий.

### Пример 7. Отображение содержимого манифеста модуля

Эти команды отображают содержимое манифеста модуля для модуля **BitsTransfer** Windows PowerShell.

Модули не обязательно должны иметь файлы манифеста. Если у них есть файл манифеста, файл манифеста требуется только для включения номера версии. Однако файлы манифестов часто предоставляют полезную информацию о модуле, его требованиях и содержимом.

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

Первая команда возвращает объект PSModuleInfo, который представляет модуль BitsTransfer. Объект сохраняется в `$m` переменной.

Вторая команда использует `Get-Content` командлет для получения содержимого файла манифеста по указанному пути. В ней используется нотация с точками для получения пути к файлу манифеста, который хранится в свойстве Path объекта. В выходных данных показано содержимое манифеста модуля.

### Пример 8. Вывод списка файлов в каталоге Module

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

Эта команда выводит список файлов в каталоге модуля. Это еще один способ определить, что входит в модуль, перед его импортом. Некоторые модули могут иметь файлы справки или файлы ReadMe, в которых описывается модуль.

### Пример 9. получение модулей, установленных на компьютере

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

Эти команды возвращают модули, которые установлены на компьютере Server01.

Первая команда использует `New-PSSession` командлет для создания **сеанса PSSession** на компьютере Server01. Команда сохраняет **PSSession** в переменной $s.

Вторая команда использует параметры **PSSession** и **ListAvailable** `Get-Module` для получения модулей в **PSSession** в `$s` переменной.

При передаче модулей из других сеансов в `Import-Module` командлет `Import-Module` импортирует модуль в текущий сеанс с помощью функции неявного удаленного взаимодействия. Это эквивалентно использованию `Import-PSSession` командлета. Вы можете использовать командлеты из модуля в рамках текущего сеанса, но команды, использующие эти командлеты, на самом деле выполняются в рамках удаленного сеанса. Дополнительные сведения см. в разделах [`Import-Module`](Import-Module.md) и [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).

### Пример 10. Управление компьютером, на котором не выполняется операционная система Windows

Команды в этом примере позволяют управлять системами хранения на удаленном компьютере, на котором не установлена операционная система Windows.
Поскольку администратор в этом примере установил поставщик WMI модуля обнаружения на на компьютере, команды CIM могут использовать значения по умолчанию, которые предназначены для поставщика.

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

Первая команда использует `New-CimSession` командлет для создания сеанса на удаленном компьютере RSDGF03. Сеанс подключается к инструментарию WMI на удаленном компьютере. Команда сохраняет сеанс CIM в `$cs` переменной.

Вторая команда использует сеанс CIM в `$cs` переменной для выполнения `Get-Module` команды на компьютере RSDGF03. С помощью параметра Name указывается модуль хранения. Команда использует оператор конвейера (|) для отправки модуля хранения в `Import-Module` командлет, который импортирует его в локальный сеанс.

Третья команда выполняет `Get-Command` командлет для `Get-Disk` команды в модуле Storage.
При импорте модуля CIM в локальный сеанс PowerShell преобразует файлы CDXML, представляющие модуль CIM, в скрипты PowerShell, которые отображаются как функции в локальном сеансе.

Четвертая команда выполняет `Get-Disk` команду. Хотя команда вводится в рамках текущего сеанса, она выполняется неявно на удаленном компьютере, с которого она была импортирована. Команда получает объекты с удаленного компьютера и возвращает их в локальный сеанс.

## PARAMETERS

### -All

Указывает, что этот командлет получает все модули в каждой папке модуля, включая вложенные модули, файлы манифеста (PSD1), файлы модуля скрипта (. PSM1) и двоичные файлы (DLL). Без этого параметра `Get-Module` получает только модуль по умолчанию в каждой папке модуля.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Цимнамеспаце

Задает пространство имен для альтернативного поставщика CIM, предоставляющего модули CIM. Значение по умолчанию — пространство имен поставщика модуля обнаружения WMI.

Этот параметр используется для получения модулей CIM с компьютеров и устройств, на которых не установлена операционная система Windows.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Цимресаурцеури

Задает альтернативное расположение для модулей CIM. Значение по умолчанию — URI ресурса поставщика модуля обнаружения WMI на удаленном компьютере.

Этот параметр используется для получения модулей CIM с компьютеров и устройств, на которых не установлена операционная система Windows.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Указывает сеанс CIM на удаленном компьютере. Введите переменную, которая содержит сеанс CIM, или команду, которая получает сеанс CIM, например команду [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .

`Get-Module` использует соединение с сеансом CIM для получения модулей с удаленного компьютера. При импорте модуля с помощью `Import-Module` командлета и использовании команд из импортированного модуля в текущем сеансе команды фактически выполняются на удаленном компьютере.

Этот параметр можно использовать для получения модулей с компьютеров и устройств, не работающих под управлением операционной системы Windows, а также для компьютеров с PowerShell, на которых не включено удаленное взаимодействие PowerShell.

Параметр **CimSession** возвращает все модули из сеанса **CIMSession**. Однако вы можете импортировать только модули CIM и CDXML.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedName

Указывает модули с именами, указанными в форме объектов **ModuleSpecification** . См. раздел "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).

Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid** — нет. Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** . два параметра являются взаимоисключающими.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ListAvailable

Указывает, что этот командлет получает все установленные модули. `Get-Module` Возвращает модули в путях, указанных в переменной среды **PSModulePath** . Без этого параметра `Get-Module` получает только те модули, которые указаны в переменной среды **PSModulePath** и загружены в текущем сеансе. Параметр **ListAvailable** не возвращает информацию о модулях, которые не найдены в переменной среды **PSModulePath**, даже если они загружены в текущий сеанс.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает имена или шаблоны имен модулей, которые получает этот командлет. Можно использовать подстановочные знаки. Можно также передать имена в `Get-Module` . Нельзя указать параметр **FullyQualifiedName** в той же команде, что и параметр **Name** .

**Имя** не может принимать GUID модуля в качестве значения.
Чтобы вернуть модули, указав идентификатор GUID, используйте вместо него **FullyQualifiedName** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -PSEdition

Возвращает модули, поддерживающие указанный выпуск PowerShell.

Допустимые значения для этого параметра:

- Рабочий стол
- Основные сведения

Командлет Get-Module проверяет свойство **CompatiblePSEditions** объекта **PSModuleInfo** на указанное значение и возвращает только те модули, для которых он задан.

> [!NOTE]
>
> - **Выпуск Desktop:** создан на базе платформы .NET Framework и обеспечивает совместимость со сценариями и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.
> - **Выпуск Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSSession

Возвращает модули из указанного управляемого пользователем сеанса PowerShell (**PSSession**). Введите переменную, которая содержит сеанс, команду, которая получает сеанс, например `Get-PSSession` команду, или команду, которая создает сеанс, например `New-PSSession` команду.

Если сеанс подключен к удаленному компьютеру, необходимо указать параметр **ListAvailable** .

`Get-Module`Команда, использующая параметр **PSSession** , эквивалентна использованию `Invoke-Command` командлета для выполнения `Get-Module -ListAvailable` команды в **PSSession**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Refresh

Указывает, что этот командлет обновляет кэш установленных команд. Кэш команд создается при запуске сеанса. Он позволяет `Get-Command` командлету получать команды из модулей, которые не импортируются в сеанс.

Этот параметр предназначен для сценариев разработки и тестирования, в которых содержимое модулей меняется с момента начала сеанса.

При указании параметра **Refresh** в команде необходимо указать **ListAvailable**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скипедитиончекк

Пропускает проверку `CompatiblePSEditions` поля.

По умолчанию Get-Module будет опускать модули в `%windir%\System32\WindowsPowerShell\v1.0\Modules` каталоге, не указанные `Core` в `CompatiblePSEditions` поле. Если этот параметр задан, то модули без `Core` будут включены, поэтому будут возвращены модули в пути модуля Windows PowerShell, несовместимые с PowerShell Core.

В macOS и Linux этот параметр не выполняет никаких действий.

Дополнительные сведения см. в разделе [about_PowerShell_Editions](About/about_PowerShell_Editions.md) .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
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

### System.String

В этот командлет можно передать имена модулей.

## Выходные данные

### System.Management.Automation.PSModuleInfo

Этот командлет возвращает объекты, представляющие модули.
При указании параметра **ListAvailable** `Get-Module` возвращает объект **модулеинфограупинг** , который является типом объекта **PSModuleInfo** , который имеет те же свойства и методы.

## ПРИМЕЧАНИЯ

- Начиная с Windows PowerShell 3,0, основные команды, входящие в PowerShell, упаковываются в модули. Исключением является **Microsoft. PowerShell. Core**— оснастка (**PSSnapin**). По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core**. Модули импортируются автоматически при первом использовании `Import-Module` . для их импорта можно использовать командлет.

- В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях PowerShell, основные команды упаковываются в оснастки (**PSSnapin**). Исключением является **Microsoft. PowerShell. Core**, который всегда является оснасткой. Кроме того, удаленные сеансы, такие как запущенные `New-PSSession` командлетом, являются сеансами предыдущих версий, включающими основные оснастки.

  Дополнительные сведения о методе **CreateDefault2** , который создает сеансы нового стиля с основными модулями, см. в разделе [метод CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).

- `Get-Module` только возвращает модули в расположениях, которые хранятся в значении переменной среды **PSModulePath** ($env:P смодулепас). `Import-Module`Командлет может импортировать модули в других местах, но `Get-Module` для их получения нельзя использовать командлет.

- Кроме того, начиная с PowerShell 3,0 в объект, который возвращает, были добавлены новые свойства, `Get-Module` которые упрощают изучение модулей даже перед их импортом. Все свойства заполняются перед импортом. К ним относятся свойства **ExportedCommands**, **експортедкмдлетс** и **експортедфунктионс** , в которых перечислены команды, экспортируемые модулем.

- Параметр **ListAvailable** возвращает только модули с правильным форматом, то есть папки, содержащие по крайней мере один файл, базовое имя которого совпадает с именем папки модуля. Базовое имя — это имя без расширения имени файла. Папки, содержащие файлы с разными именами, считаются контейнерами, но не модулями.

  Для получения модулей, которые реализуются в виде DLL-файлов, но не заключаются в папку модуля, укажите оба параметра: **ListAvailable** и **ALL** .

- Для использования функции сеанса CIM на удаленном компьютере должен быть установлен компонент удаленного взаимодействия WS-Management и инструментарий управления Windows (WMI), который представляет собой реализацию стандарта CIM корпорации Майкрософт. На компьютере должен быть также поставщик WMI обнаружения модулей или другой поставщик WMI с теми же основными возможностями.

  Можно использовать сеанс CIM на компьютерах, на которых не установлена операционная система Windows и на компьютерах Windows с PowerShell, но удаленное взаимодействие PowerShell не включено.

  Можно также использовать параметры CIM для получения модулей CIM с компьютеров, на которых включено удаленное взаимодействие PowerShell. Сюда входит локальный компьютер. При создании сеанса CIM на локальном компьютере для создания сеанса в PowerShell используется DCOM, а не WMI.

## Связанные ссылки

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[about_Modules](About/about_Modules.md)

[Get-PSSession](Get-PSSession.md)

[Import-Module](Import-Module.md)

[Import-PSSession](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[New-PSSession](New-PSSession.md)

[Remove-Module](Remove-Module.md)

[about_PowerShell_Editions](About/about_PowerShell_Editions.md)
