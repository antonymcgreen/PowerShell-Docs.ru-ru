---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: ef5bf676e261e7a4267980a3e87753724ca9bf42
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228150"
---
# Import-PSSession

## Краткий обзор
Импортирует команды из другого сеанса в текущий.

## SYNTAX

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## DESCRIPTION

Командлет **Import-PSSession** импортирует команды, такие как командлеты, функции и псевдонимы, из сеанса PSSession на локальном или удаленном компьютере в текущий сеанс.
Можно импортировать любую команду, которую командлет Get-Command может найти в сеансе PSSession.

Команда **Import-PSSession** используется для импорта команд из настраиваемой оболочки, например оболочки Microsoft Exchange Server, или из сеанса, содержащего модули и оснастки PowerShell, а также другие элементы, которые не находятся в текущем сеансе.

Чтобы импортировать команды, сначала используйте командлет New-PSSession, чтобы создать сеанс PSSession.
После этого используйте командлет **Import-PSSession** для импорта команд.
По умолчанию **Import-PSSession** импортирует все команды, за исключением команд, которые имеют такие же имена, как и команды в текущем сеансе.
Чтобы импортировать все команды, используйте параметр *AllowClobber* .

Импортированные команды можно использовать точно так же, как и любую команду в сеансе.
При использовании импортированных команд импортированная часть команды выполняется неявно в сеансе, из которой она была импортирована.
Однако удаленные операции полностью обрабатываются PowerShell.
Вам даже не нужно помнить о них, за исключением того, что нужно поддерживать подключение к другому сеансу (PSSession) открытым.
Если его закрыть, импортированные команды перестают быть недоступными.

Поскольку импортированные команды могут выполняться дольше локальных, **Import-PSSession** добавляет в каждую импортированную команду параметр *AsJob* .
Этот параметр позволяет выполнять команду в качестве фонового задания PowerShell.
Дополнительные сведения см. в разделе about_Jobs.

При использовании командлета **Import-PSSession** PowerShell добавляет импортированные команды во временный модуль, который существует только в сеансе, и возвращает объект, представляющий модуль.
Чтобы создать постоянный модуль, который можно использовать в будущих сеансах, используйте командлет Export-PSSession.

Командлет **Import-PSSession** использует функцию неявного удаленного взаимодействия PowerShell.
При импорте команд в текущий сеанс они выполняются неявно в исходном сеансе или в аналогичном сеансе на исходном компьютере.

Начиная с Windows PowerShell 3,0, можно использовать командлет Import-Module для импорта модулей из удаленного сеанса в текущий сеанс.
Эта функция использует неявное удаленное взаимодействие.
Это эквивалентно использованию **Import-PSSession** для импорта выбранных модулей из удаленного сеанса в текущий сеанс.

## Примеры

### Пример 1. импорт всех команд из PSSession

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

Эта команда импортирует все команды из PSSession на компьютере Server01 в текущий сеанс, за исключением команд, которые имеют такие же имена, как и команды в текущем сеансе.

Поскольку эта команда не использует параметр *CommandName* , она также импортирует все необходимые для импортированных команд данные форматирования.

### Пример 2. Импорт команд, заканчивающихся заданной строкой

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

Эти команды импортируют команды, имена которых заканчиваются на "-test", из PSSession в локальный сеанс, а затем показывают, как использовать импортированный командлет.

Первая команда использует командлет New-PSSession для создания сеанса PSSession.
Он сохраняет PSSession в переменной $S.

Вторая команда использует командлет **Import-PSSession** для импорта команд из PSSession в $S в текущий сеанс.
Она использует параметр *CommandName* , чтобы указать команды с существительным Test, и параметр *FormatTypeName* , чтобы импортировать данные форматирования для команд Test.

Третья и четвертая команды используют импортированные команды в текущем сеансе.
Поскольку импортированные команды фактически добавляются в текущий сеанс, для их выполнения используется локальный синтаксис.
Для выполнения импортированной команды не нужно использовать командлет Invoke-Command.

### Пример 3. импорт командлетов из PSSession

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

Этот пример показывает, что импортированные командлеты можно использовать точно так же, как и локальные командлеты.

Эти команды импортируют командлеты New-Test и Get-Test из PSSession на компьютере Server01 и командлет Set-Test из PSSession на компьютере Server02.

Несмотря на то, что командлеты были импортированы из разных сеансов PSSession, можно без ошибок передать объект из одного командлета в другой.

### Пример 4. Запуск импортированной команды в качестве фонового задания

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

В этом примере показано, как выполнять импортированную команду в качестве фонового задания.

Поскольку импортированные команды могут выполняться дольше локальных, **Import-PSSession** добавляет в каждую импортированную команду параметр *AsJob* .
Параметр *AsJob* позволяет выполнить команду в качестве фонового задания.

Первая команда создает сеанс PSSession на компьютере Server01 и сохраняет объект PSSession в переменной $S.

Вторая команда использует **Import-PSSession** для импорта командлетов теста из PSSession в $S в текущий сеанс.

Третья команда использует параметр *AsJob* импортированного командлета New-Test для запуска команды New-Test в качестве фонового задания.
Команда сохраняет возвращаемый New-Test объект задания в переменной $batch.

Четвертая команда использует командлет Receive-Job для получения результатов задания в переменной $batch.

### Пример 5. импорт командлетов и функций из модуля PowerShell

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

В этом примере показано, как импортировать командлеты и функции из модуля PowerShell на удаленном компьютере в текущий сеанс.

Первая команда создает сеанс PSSession на компьютере Server01 и сохраняет его в переменной $S.

Вторая команда использует командлет **Invoke-Command** для выполнения команды Import-Module в сеансе PSSession в $S.

Как правило, модуль будет добавлен во все сеансы командой **Import-Module** в профиле PowerShell, но профили не будут выполняться в PSSession.

Третья команда использует параметр *module*  команды **Import-PSSession** для импорта командлетов и функций в модуль в текущий сеанс.

### Пример 6. Создание модуля во временном файле

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

В этом примере показано, что **Import-PSSession** создает модуль во временном файле на диске.
В нем также показано, что все команды преобразуются в функции перед их импортом в текущий сеанс.

Команда использует командлет **Import-PSSession** для импорта командлета Get-Date и функции сеарчхелп в текущий сеанс.

Командлет **Import-PSSession** возвращает объект **PSModuleInfo** , представляющий временный модуль.
Значение **Path** свойства показывает, что **Import-PSSession** создал во временной папке файл модуля сценариев (PSM1).
Свойство **ExportedFunctions** показывает, что командлет **Get-Date** и функция SearchHelp были импортированы как функции.

### Пример 7. выполнение команды, скрытой импортированной командой

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

В этом примере показано, как выполнить команду, скрытую импортированной командой.

Первая команда импортирует командлет Get-Date из PSSession в переменной $S.
Поскольку текущий сеанс включает в себя командлет **Get-Date** , в команде необходимо указать параметр *AllowClobber* .

Вторая команда использует параметр **ALL** командлета Get-Command для получения всех команд **Get-Date** в текущем сеансе.
Выходные данные показывают, что сеанс включает в себя исходный командлет **Get-Date** и функцию **Get-Date** .
Функция **Get-Date** запускает импортированный командлет **Get-Date** в сеансе PSSession в $S.

Третья команда выполняет команду **Get-Date** .
Поскольку функции имеют приоритет над командлетами, PowerShell выполняет импортированную функцию **Get-Date** , которая возвращает Юлианскую дату.

Четвертая и пятая команды показывают, как использовать полное имя для выполнения команды, которая скрыта импортированной командой.

Четвертая команда возвращает имя оснастки PowerShell, которая добавила исходный командлет **Get-Date** в текущий сеанс.

Пятая команда использует полное имя командлета **Get-Date** , учитывающее оснастку, для запуска команды **Get-Date** .

Дополнительные сведения о приоритете команд и скрытых командах см. в разделе about_Command_Precedence.

### Пример 8. Импорт команд с определенной строкой в именах

```
PS C:\> Import-PSSession -Session $S -CommandName *Item* -AllowClobber
```

Эта команда импортирует команды, имена которых включают элемент из PSSession в $S.
Так как команда содержит параметр *CommandName* , но не параметр *форматтипедата* , импортируется только команда.

Воспользуйтесь этой командой при использовании **Import-PSSession** для выполнения команды на удаленном компьютере, когда в текущем сеансе уже имеются данные форматирования для этой команды.

### Пример 9. Использование параметра module для определения команд, импортированных в сеанс

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

Эта команда показывает, как использовать параметр *module* командлета **Get-Command** , чтобы узнать, какие команды были импортированы в сеанс с помощью команды **Import-PSSession** .

Первая команда использует командлет **Import-PSSession** для импорта команд, имена которых содержат "BITS", из сеанса PSSession в переменной $S.
Команда **Import-PSSession** возвращает временный модуль и сохраняет его в переменной $m.

Вторая команда использует командлет Get-Command для получения команд, экспортируемых модулем в переменной $M.

Параметр *Module* принимает строковое значение, которое предназначено для имени модуля.
Однако при отправке объекта модуля PowerShell использует метод **ToString** для объекта Module, который возвращает имя модуля.

Команда **Get-Command** эквивалентна `Get-Command $M.Name` ".

## PARAMETERS

### -AllowClobber

Указывает, что этот командлет импортирует указанные команды, даже если они имеют те же имена, что и команды в текущем сеансе.

При импорте команды с таким же именем, что и у команды в текущем сеансе, импортированная команда скрывает или заменяет собой исходную команду.
Дополнительные сведения см. в разделе about_Command_Precedence.

По умолчанию **Import-PSSession** не импортирует команды, которые имеют имя, совпадающее с именем команды в текущем сеансе.

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

### -ArgumentList

Задает массив команд, полученный в результате использования заданных аргументов (значений параметров).

Например, чтобы импортировать вариант команды Get-Item в сертификате (CERT:) диск в PSSession в $S введите `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .

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

### — Сертификат

Задает сертификат клиента, который используется для подписи файлов формата (*.Format.ps1xml) или файлов модуля сценариев (PSM1) во временном модуле, создаваемом **Import-PSSession** .

Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.

Чтобы найти сертификат, используйте командлет Get-PfxCertificate или используйте командлет Get-ChildItem в сертификате (CERT:). диск.
Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandName

Задает команды с указанными именами или шаблонами имен.
Разрешено использовать подстановочные знаки.
Используйте *CommandName* или его псевдоним, *имя* .

По умолчанию **Import-PSSession** импортирует все команды из сеанса, за исключением команд, которые имеют такие же имена, как и команды в текущем сеансе.
Это предотвращает скрытие или замену команд в текущем сеансе импортированными командами.
Чтобы импортировать все команды, даже те, которые скрыты или заменены другими командами, используйте параметр *AllowClobber* .

При использовании параметра *CommandName* файлы форматирования для команд не импортируются, пока не будет задан параметр *FormatTypeName* .
Аналогично, если вы используете параметр *FormatTypeName* , команды не импортируются, пока не будет задан параметр *CommandName* .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType

Указывает тип командных объектов.
Значение по умолчанию — Cmdlet.
Используйте параметр *CommandType* или его псевдоним *Type* .
Допустимые значения для этого параметра:

- Псевдоним.
Псевдонимы PowerShell в удаленном сеансе.
- Все.
Командлеты и функции в удаленном сеансе.
- приложение.
Все файлы, кроме файлов PowerShell, в путях, указанных в переменной среды PATH ($env:p ь) в удаленном сеансе, включая txt, exe и DLL-файлы.
- Командлет.
Командлеты в удаленном сеансе.
Значение по умолчанию — "Cmdlet".
- Екстерналскрипт.
PS1-файлы в путях, указанных в переменной среды Path ($env:путь) в удаленном сеансе.
- Фильтр и функция.
Функции PowerShell в удаленном сеансе.
- Скрипт.
Блоки сценариев в удаленном сеансе.

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableNameChecking

Указывает, что этот командлет подавляет сообщение, выдающее предупреждение при импорте командлета или функции, имя которой включает неутвержденную команду или запрещенный символ.

По умолчанию, когда импортируемый модуль экспортирует командлеты или функции с неутвержденными командами в именах, PowerShell выводит следующее предупреждающее сообщение:

"Внимание! некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми.
Используйте параметр Verbose, чтобы получить дополнительные сведения, или введите Get-Verb, чтобы просмотреть список утвержденных глаголов".

Это сообщение является всего лишь предупреждением.
Импорт осуществляется для всего модуля, включая недопустимые команды.
Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.

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

### -FormatTypeName

Задает инструкции по форматированию для указанных Microsoft .NET типов платформы.
Введите имена типов.
Разрешено использовать подстановочные знаки.

Значением этого параметра должно быть имя типа, возвращаемого командой Get-FormatData в сеансе, из которого команда импортируется.
Чтобы получить все данные форматирования в удаленном сеансе, введите *.

Если команда не содержит ни параметр *CommandName* , ни *FormatTypeName* , командлет Import **-PSSession** импортирует инструкции форматирования для всех типов .NET Framework, возвращаемых командой **Get-FormatData** в удаленном сеансе.

Если вы используете параметр *FormatTypeName* , команды не импортируются, пока не будет задан параметр *CommandName* .

Аналогично, при использовании параметра *CommandName* файлы форматирования для команд не импортируются, пока не будет задан параметр *FormatTypeName* .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedModule

Задает модули с именами, указанными в форме объектов **ModuleSpecification** (описанных в разделе "Примечания" [конструктора ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290) в библиотеке MSDN).
Например, параметр *FullyQualifiedModule* принимает имя модуля, указанное в формате @ {ModuleName = "ModuleName"; ", ИД =" version_number "} или @ {ModuleName =" ModuleName "; "ИД" = "version_number"; GUID = "GUID"}.
Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.

Нельзя указать параметр *FullyQualifiedModule* в той же команде, что и параметр *module* ; два параметра являются взаимоисключающими.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Module

Указывает и массив команд в оснастках и модулях PowerShell.
Введите имена оснасток и модулей.
Использовать подстановочные знаки запрещено.

**Import-PSSession** не может импортировать поставщиков из оснастки.

Дополнительные сведения см. в статьях about_PSSnapins и [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Префикс

Задает префикс для существительных в именах импортированных команд.

Используйте этот параметр, чтобы избежать конфликтов имен, которые могут возникать, когда разные команды в сеансе имеют одинаковое имя.

Например, если указать префикс Remote, а затем импортировать командлет Get-Date, то этот командлет будет известен в сеансе как Get-Ремотедате и не будет путать с исходным командлетом **Get-Date** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Указывает **сеанс PSSession** , из которого импортируются командлеты.
Введите переменную, которая содержит объект сеанса, или команду, которая получает объект сеанса, например New-PSSession или Get-PSSession команду.
Можно указать только один сеанс.
Этот параметр обязателен.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### System.Management.Automation.PSModuleInfo

Командлет **Import-PSSession** возвращает тот же объект модуля, который New-Module и Get-Module вернул.
Однако импортированный модуль является временным и существует только в текущем сеансе.
Чтобы создать постоянный модуль на диске, используйте командлет Export-PSSession.

## ПРИМЕЧАНИЯ

* **Import-PSSession** основывается на инфраструктуре удаленного взаимодействия PowerShell. Для использования этого командлета компьютер должен быть настроен на удаленное взаимодействие WS-Management. Дополнительные сведения см. в разделе about_Remote и about_Remote_Requirements.
* **Import-PSSession** не импортирует переменные или поставщики PowerShell.
* При импорте команд, которые имеют те же имена, что и команды в текущем сеансе, импортированные команды в сеансе могут скрывать псевдонимы, функции и командлеты, а также заменять функции и переменные. Во избежание конфликтов имен используйте параметр *Prefix* . Дополнительные сведения см. в разделе about_Command_Precedence.
* **Import-PSSession** преобразует все команды в функции перед их импортом. В результате импортированные команды работают немного иначе, чем если бы они сохранили свой исходный тип команды. Например, если импортировать командлет из PSSession и затем импортировать командлет с таким же именем из модуля или оснастки, импортированный из PSSession командлет всегда выполняется по умолчанию, поскольку функции имеют приоритет над командлетами. И наоборот, если импортировать псевдоним в сеанс, где уже есть псевдоним с таким же именем, всегда используется исходный псевдоним, поскольку псевдонимы имеют приоритет над функциями. Дополнительные сведения см. в разделе about_Command_Precedence.
* **Import-PSSession** использует командлет Write-Progress для просмотра хода выполнения команды. Во время выполнения команды может отображаться индикатор выполнения .
* Чтобы найти команды для импорта, **Import-PSSession** использует командлет Invoke-Command для выполнения команды Get-Command в сеансе PSSession. Чтобы получить данные форматирования для команд, используется командлет Get-FormatData. При выполнении команды **Import-PSSession** могут отображаться сообщения об ошибках из этих командлетов. Кроме того, командлет **Import-PSSession** не может импортировать команды из PSSession, не включающего в себя Get-Command, Get-FormatData, Select-Object и Get-Help.
* Импортированные команды имеют те же ограничения, что и другие удаленные команды, включая невозможность запуска программы с пользовательским интерфейсом, например "Блокнот".
* Так как профили PowerShell не выполняются в PSSession, команды, которые профиль добавляет в сеанс, недоступны для **импорта-PSSession** . Для импорта команд из профиля используйте команду Invoke-Command, чтобы вручную запустить профиль в PSSession перед импортом команд.
* Временный модуль, создаваемый **Import-PSSession** , может включать в себя файл форматирования, даже если команда не импортирует данные форматирования. Если команда не импортирует данные форматирования, все создаваемые файлы форматирования не будут содержать данные форматирования.
* Для использования **Import-PSSession** политика выполнения в текущем сеансе должна отличаться от Restricted и AllSigned, так как создаваемый **Import-PSSession** временный модуль содержит неподписанные файлы сценариев, которые запрещены в этих политиках. Чтобы использовать командлет **Import-PSSession** без изменения политики выполнения для локального компьютера, используйте параметр *Scope* из Set-ExecutionPolicy, чтобы задать менее ограниченную политику выполнения для одного процесса.
* В Windows PowerShell 2.0 разделы справки для команд, которые импортируются из другого сеанса, не включают префикс, назначенный с помощью параметра *Prefix* . Чтобы получить справку для импортированной команды Windows PowerShell 2.0, используйте исходное имя команды (без префикса).

## Связанные ссылки

[Export-PSSession](Export-PSSession.md)
