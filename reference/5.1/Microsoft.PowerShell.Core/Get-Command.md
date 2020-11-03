---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command;
ms.openlocfilehash: daa58a732dafb11fa8f6ce3c20965aebcce55844
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226693"
---
# Get-Command;

## Краткий обзор
Получает все команды.

## SYNTAX

### CmdletSet (по умолчанию)

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### AllCommandSet

```
Get-Command [[-Name] <String[]>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-CommandType <CommandTypes>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>]
 [-All] [-ListImported] [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Command`Командлет получает все команды, установленные на компьютере, включая командлеты, псевдонимы, функции, фильтры, сценарии и приложения. `Get-Command` Получает команды из модулей и команд PowerShell, импортированных из других сеансов. Чтобы получить только те команды, которые были импортированы в текущий сеанс, используйте параметр **ListImported**.

Без параметров `Get-Command` получает все командлеты, функции и псевдонимы, установленные на компьютере. `Get-Command *` Возвращает все типы команд, включая все файлы, не относящиеся к PowerShell, в переменной среды PATH ( `$env:Path` ), которая отображается в типе команды приложения.

`Get-Command` При этом используется точное имя команды без подстановочных знаков, автоматически импортируется модуль, содержащий команду, чтобы можно было использовать команду немедленно. Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение. Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

`Get-Command` Получает данные непосредственно из кода команды, в отличие от `Get-Help` , который получает сведения из разделов справки.

Начиная с Windows PowerShell 5,0, `Get-Command` по умолчанию в результатах командлета отображается столбец **версии** . В класс **CommandInfo** было добавлено новое свойство **Version** .

## Примеры

### Пример 1. получение командлетов, функций и псевдонимов

Эта команда возвращает командлеты, функции и псевдонимы PowerShell, установленные на компьютере.

```powershell
Get-Command
```

### Пример 2. получение команд в текущем сеансе

Эта команда использует параметр **ListImported** , чтобы получить только команды в текущем сеансе.

```powershell
Get-Command -ListImported
```

### Пример 3. получение командлетов и их отображение по порядку

Эта команда получает все командлеты, сортирует их в алфавитном порядке по существительным в имени командлета, а затем отображает их в группах на базе существительных. Это помогает найти командлеты для задачи.

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### Пример 4. получение команд в модуле

Эта команда использует параметр **module** для получения команд в модулях Microsoft. PowerShell. Security и Microsoft. PowerShell. Utility.

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### Пример 5. Получение сведений о командлете

Эта команда возвращает сведения о `Get-AppLockerPolicy` командлете. Она также импортирует модуль **AppLocker** , который добавляет все команды в модуле **AppLocker** в текущий сеанс.

```powershell
Get-Command Get-AppLockerPolicy
```

Если модуль импортируется автоматически, результат аналогичен результату при использовании командлета Import-Module.
Модуль может добавить команды, типы и файлы форматирования, а также запустить скрипты в сеансе. Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение. Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

### Пример 6. получение синтаксиса командлета

Эта команда использует параметры **ArgumentList** и **синтаксиса** для получения синтаксиса `Get-ChildItem` командлета, когда он используется на диске CERT:. Диск CERT: — это диск PowerShell, который поставщик сертификатов добавляет в сеанс.

```powershell
Get-Command Get-Childitem -Args Cert: -Syntax
```

При сравнении синтаксиса, отображаемого в выходных данных, с синтаксисом, который отображается при пропуске параметра **args** ( **ArgumentList** ), вы увидите, что **поставщик сертификатов** добавляет динамический параметр **CodeSigningCert** в `Get-ChildItem` командлет.

Дополнительные сведения о поставщике сертификатов см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

### Пример 7. получение динамических параметров

Команда в примере использует `Get-DynamicParameters` функцию для получения динамических параметров, которые поставщик сертификатов добавляет к `Get-ChildItem` командлету при его использовании на диске CERT:.

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

`Get-DynamicParameters`Функция в этом примере получает динамические параметры командлета. Это альтернативный метод, использованный в предыдущем примере. Динамический параметр можно добавить в командлет с помощью другого командлета или поставщика.

### Пример 8. получение всех команд всех типов

Эта команда возвращает все команды всех типов на локальном компьютере, включая исполняемые файлы, в пути переменной среды **path** ( `$env:path` ).

```powershell
Get-Command *
```

Она возвращает для каждого файла объект **ApplicationInfo** (System.Management.Automation.ApplicationInfo), а не объект **FileInfo** (System.IO.FileInfo).

### Пример 9. получение командлетов с помощью имени и типа параметра

Эта команда получает командлеты с параметром, имя которого включает проверку подлинности и тип **AuthenticationMechanism**.

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

Для поиска командлетов, которые позволяют указать метод, использующийся для проверки подлинности пользователя, можно использовать команду подобным образом.

Параметр **ParameterType** разделяет параметры, которые получают значение **AuthenticationMechanism** от тех параметров, которые получают параметр **AuthenticationLevel** , даже если они имеют одинаковые имена.

### Пример 10. получение псевдонима

В этом примере показано, как использовать `Get-Command` командлет с псевдонимом.

```powershell
Get-Command dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

Хотя он обычно используется в командлетах и функциях, `Get-Command` также получает скрипты, функции, псевдонимы и исполняемые файлы.

В выходных данных команды показано специальное представление значения свойства **Name** для псевдонимов. В представлении показан псевдоним и полное имя команды.

### Пример 11. получение всех экземпляров команды Notepad

В этом примере используется параметр **ALL** `Get-Command` командлета для отображения всех экземпляров команды «Notepad» на локальном компьютере.

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

Параметр **All** полезен, если в сеансе есть больше одной команды с одинаковым именем.

Начиная с Windows PowerShell 3,0, по умолчанию, когда сеанс включает несколько команд с одинаковым именем, `Get-Command` получает только команду, которая выполняется при вводе имени команды. При использовании параметра **ALL** `Get-Command` получает все команды с указанным именем и возвращает их в порядке очередности выполнения. Чтобы запустить команду, которая не является первой в списке, введите полный путь к команде.

Дополнительные сведения о приоритете команд см. в разделе [about_Command_Precedence](About/about_Command_Precedence.md).

### Пример 12. Получение имени модуля, содержащего командлет

Эта команда возвращает имя модуля, в котором `Get-Date` был создан командлет.
Команда использует свойство **ModuleName** всех команд.

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

Этот формат команды работает с командами в модулях PowerShell, даже если они не импортированы в сеанс.

### Пример 13. получение командлетов и функций с типом выходных данных

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

Эта команда получает командлеты и функции, содержащие тип выходных данных и тип возвращаемых объектов.

Первая часть команды получает все командлеты.
Оператор конвейера (|) отправляет командлеты `Where-Object` командлету, который выбирает только те, в которых заполнено свойство **OutputType** .
Другой конвейерный оператор отправляет выбранные объекты командлета в `Format-List` командлет, который отображает имя и тип выходных данных каждого командлета в списке.

Свойство **OutputType** объекта **CommandInfo** имеет значение, отличное от NULL, только если код командлета определяет для командлета атрибут **OutputType**.

### Пример 14. получение командлетов, которые принимают в качестве входных данных конкретный тип объекта

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

Эта команда находит командлеты, которые получают объекты сетевого адаптера в качестве выходных данных. Этот формат команды можно использовать для поиска командлетов, которые принимают тип объектов, возвращаемый любой командой.

Команда использует внутреннее свойство **PSTypeNames** всех объектов, которые получают типы, описывающие объект. Чтобы получить свойство сетевого адаптера **PSTypeNames** , а не свойство коллекции сетевых адаптеров **PSTypeNames** , команда использует нотацию массива, чтобы получить первый сетевой адаптер, который возвращает командлет.
Чтобы получить свойство сетевого адаптера **PSTypeNames** , а не свойство коллекции сетевых адаптеров **PSTypeNames** , команда использует нотацию массива, чтобы получить первый сетевой адаптер, который возвращает командлет.

## PARAMETERS

### -All

Указывает, что этот командлет получает все команды, включая команды того же типа с тем же именем. По умолчанию `Get-Command` получает только команды, которые выполняются при вводе имени команды.

Дополнительные сведения о методе, используемом PowerShell для выбора команды, которая будет выполняться, если несколько команд имеют одинаковые имена, см. в разделе [about_Command_Precedence](About/about_Command_Precedence.md).
Сведения об именах команд с указанием модуля и выполнении команд, которые не выполняются по умолчанию из-за конфликта имен, см. в разделе [about_Modules](About/about_Modules.md).

Этот параметр впервые появился в Windows PowerShell 3.0.

В Windows PowerShell 2,0 `Get-Command` по умолчанию получает все команды.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ArgumentList

Задает массив аргументов. Этот командлет получает сведения о командлете или функции при их использовании с указанными параметрами ("arguments"). Псевдоним для **ArgumentList** — **Args**.

Чтобы обнаружить динамические параметры, доступные только при использовании некоторых других параметров, задайте для параметра **ArgumentList** значение, которое вызывает динамические параметры.

Чтобы определить динамические параметры, которые поставщик добавляет к командлету, присвойте параметру **ArgumentList** путь на диске поставщика, например WSMan:, HKLM: или CERT:. Если команда является командлетом поставщика PowerShell, введите в каждой команде только один путь. Командлеты поставщика возвращают только динамические параметры для первого пути в значении **ArgumentList**. Дополнительные сведения о командлетах поставщика см. в разделе [about_Providers](About/about_Providers.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType

Указывает типы команд, которые получает этот командлет. Введите один или несколько типов команд. Используйте параметр **CommandType** или его псевдоним **Type**. По умолчанию `Get-Command` получает все командлеты, функции и псевдонимы.

Допустимые значения для этого параметра:

- Псевдоним. Возвращает псевдонимы всех команд PowerShell. Дополнительные сведения см. в разделе [about_Aliases](About/about_Aliases.md).
- Все. Получает все типы команд. Значение этого параметра эквивалентно значению `Get-Command *` .
- приложение. Возвращает файлы, не относящиеся к PowerShell, в путях, указанных в переменной среды **path** ($env:p ь), включая txt, exe и DLL-файлы. Дополнительные сведения о переменной среды **Path** см. в разделе about_Environment_Variables.
- Командлет. Получает все командлеты.
- Екстерналскрипт. Получает все PS1-файлы в путях, указанных в переменной среды **Path** ($env:path).
- Фильтр и функция. Возвращает все расширенные и простые функции и фильтры PowerShell.
- Скрипт. Получает все блоки скриптов. Чтобы получить скрипты PowerShell (PS1-файлы), используйте значение Екстерналскрипт.
- Процессов. Получает все рабочие процессы. Дополнительные сведения о рабочих процессах см. в статье "Общие сведения о рабочем процессе Windows PowerShell".

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullyQualifiedModule

Указывает модули с именами, указанными в форме объектов **ModuleSpecification** , описанной в разделе **"Примечания"** [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).
Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.

Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** . Два параметра являются взаимоисключающими.

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

### -ListImported

Указывает, что этот командлет получает только команды в текущем сеансе.

Начиная с PowerShell 3,0, по умолчанию `Get-Command` получает все установленные команды, включая, но не ограниченные, команды в текущем сеансе. В PowerShell 2,0 он возвращает только команды в текущем сеансе.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Module

Указывает массив модулей. Этот командлет возвращает команды, которые поступили из указанных модулей или оснасток. Введите имена модулей или оснасток.

Этот параметр принимает строковые значения, но значение этого параметра также может быть объектом **PSModuleInfo** или **PSSnapinInfo** , таким как объекты, `Get-Module` `Get-PSSnapin` `Import-PSSession` возвращаемые командлетами, и.

На этот параметр можно ссылаться по его имени, **Module** или псевдониму **PSSnapin**.
Выбранное имя параметра не влияет на выходные данные команды.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Name

Задает массив имен. Этот командлет возвращает только команды с указанным именем. Введите имя или шаблон имени. Можно использовать подстановочные знаки.

Чтобы получить команды с одинаковым именем, используйте параметр **All**. Если две команды имеют одинаковое имя, по умолчанию `Get-Command` получает команду, которая выполняется при вводе имени команды.

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Noun

Указывает массив существительных команд. Этот командлет возвращает команды, которые включают командлеты, функции и псевдонимы, имена которых содержат указанное существительное. Введите одно или несколько существительных или шаблонов существительных. Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ParameterName

Указывает массив имен параметров. Этот командлет возвращает команды в сеансе с указанными параметрами. Введите имена параметров или псевдонимы параметров. Поддерживаются подстановочные знаки.

Параметры **ParameterName** и **ParameterType** ищут только команды в текущем сеансе.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ParameterType

Указывает массив имен параметров. Этот командлет возвращает команды в сеансе, которые имеют параметры указанного типа. Введите полное имя или частичное имя типа параметра. Поддерживаются подстановочные знаки.

Параметры **ParameterName** и **ParameterType** ищут только команды в текущем сеансе.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ShowCommandInfo

Указывает, что этот командлет отображает сведения о команде.

Этот параметр появился в Windows PowerShell 5,0.

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

### -Syntax

Указывает, что этот командлет получает только следующие указанные данные о команде:

- Псевдоним. Возвращает стандартное имя.
- Образующих. Возвращает синтаксис.
- Функции и фильтры. Возвращает определение функции.
- Скрипты и приложения или файлы. Возвращает путь и имя файла.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TotalCount

Указывает количество команд для получения. Этот параметр можно использовать, чтобы ограничить выходные данные команды.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Verb

Задает массив команд. Этот командлет возвращает команды, которые включают командлеты, функции и псевдонимы, имеющие имена, включающие указанную команду. Введите один или несколько глаголов или шаблонов глаголов. Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](About/about_CommonParameters.md).

## Входные данные

### System.String

В этот командлет можно передать имена команд по конвейеру.

## Выходные данные

### System.Management.Automation.CommandInfo

Этот командлет возвращает объекты, производные от класса **CommandInfo** . Тип возвращаемого объекта зависит от типа команды, которая `Get-Command` получает.

### System.Management.Automation.AliasInfo

Представляет псевдонимы.

### System.Management.Automation.ApplicationInfo

Представляет приложения и файлы.

### System.Management.Automation.CmdletInfo

Представляет командлеты.

### System.Management.Automation.FunctionInfo

Представляет функции и фильтры.

### System.Management.Automation.WorkflowInfo

Представляет рабочие процессы.

## ПРИМЕЧАНИЯ

* Если в сеансе доступно более одной команды с одним и тем же именем, `Get-Command` Возвращает команду, которая выполняется при вводе имени команды. Для получения команд с одинаковыми именами, перечисленными в списке порядок выполнения, используйте параметр **ALL** . Дополнительные сведения см. в разделе [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).
* При автоматическом импорте модуля этот результат будет таким же, как и при использовании `Import-Module` командлета. Модуль может добавить команды, типы и файлы форматирования, а также запустить скрипты в сеансе.
  Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение. Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

## Связанные ссылки

[Export-PSSession](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[Get-Help](Get-Help.md)

[Get-Member](../Microsoft.PowerShell.Utility/Get-Member.md)

[Get-PSDrive](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[Import-PSSession](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[about_Command_Precedence](About/about_Command_Precedence.md)
