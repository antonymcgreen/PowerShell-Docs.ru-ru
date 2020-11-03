---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: ff1b709b363684e27a1f4eb8fdeada2d5ae1d588
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226182"
---
# Export-PSSession

## Краткий обзор

Экспортирует команды из другого сеанса и сохраняет их в модуле PowerShell.

## SYNTAX

### Все

```
Export-PSSession [-OutputModule] <String> [-Force] [-Encoding <Encoding>]
 [[-CommandName] <String[]>] [-AllowClobber] [-ArgumentList <Object[]>]
 [-CommandType <CommandTypes>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-FormatTypeName] <String[]>] [-Certificate <X509Certificate2>] [-Session] <PSSession>
 [<CommonParameters>]
```

## DESCRIPTION

`Export-PSSession`Командлет получает командлеты, функции, псевдонимы и другие типы команд из другого сеанса PowerShell (PSSession) на локальном или удаленном компьютере и сохраняет их в модуле PowerShell. Чтобы добавить команды из модуля в текущий сеанс, используйте `Import-Module` командлет.

В отличие от `Import-PSSession` , которое импортирует команды из другого PSSession в текущий сеанс, `Export-PSSession` сохраняет команды в модуле. Команды не импортируются в текущий сеанс.

Чтобы экспортировать команды, используйте `New-PSSession` командлет, чтобы создать сеанс PSSession с командами, которые необходимо экспортировать. Затем с помощью `Export-PSSession` командлета экспортируйте команды.

Чтобы избежать конфликтов имен команд, по умолчанию для `Export-PSSession` используется параметр экспортировать все команды, за исключением команд, существующих в текущем сеансе. Для указания экспортируемых команд можно использовать параметр **CommandName** .

`Export-PSSession`Командлет использует функцию неявного удаленного взаимодействия PowerShell. При импорте команд в текущий сеанс они выполняются неявно в исходном сеансе или в аналогичном сеансе на исходном компьютере.

## Примеры

### Пример 1. экспорт команд из PSSession

В этом примере создается новый сеанс PSSession с локального компьютера на компьютер Server01. Все команды, за исключением тех, которые существуют в текущем сеансе, экспортируются в модуль с именем Server01 на локальном компьютере. Экспорт включает данные форматирования для команд.

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

`New-PSSession`Команда создает сеанс PSSession на компьютере Server01. Сеанс PSSession хранится в `$S` переменной. `Export-PSSession`Команда экспортирует `$S` команды и данные форматирования переменной в модуль Server01.

### Пример 2. экспорт команд Get и Set

В этом примере все `Get` команды и экспортируются `Set` с сервера.

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

Эти команды экспортируют `Get` `Set` команды и из оснастки Microsoft Exchange Server на удаленном компьютере в модуль Exchange в `$PSHOME\Modules` каталоге на локальном компьютере.
Размещение модуля в `$PSHOME\Modules` каталоге делает его доступным для всех пользователей компьютера.

### Пример 3. экспорт команд с удаленного компьютера

В этом примере командлеты экспортируются из сеанса PSSession на удаленном компьютере и сохраняются в модуль на локальном компьютере. Командлеты из модуля добавляются в текущий сеанс, чтобы их можно было использовать.

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

`New-PSSession`Команда создает сеанс PSSession на компьютере Server01 и сохраняет его в `$S` переменной. `Export-PSSession`Команда экспортирует командлеты, имена которых начинаются с сеанса PSSession в, в `$S` модуль TestCmdlets на локальном компьютере.

`Remove-PSSession`Командлет удаляет сеанс PSSession `$S` из текущего сеанса. Эта команда показывает, что сеанс PSSession не должен быть активным для использования команд, импортированных из сеанса. `Import-Module`Командлет добавляет командлеты в модуль TestCmdlets в текущий сеанс. Команда может быть запущена в любом сеансе в любое время.

`Get-Help`Командлет возвращает справку для командлетов, имена которых начинаются с Test. После добавления команд в модуль в текущий сеанс можно использовать `Get-Help` `Get-Command` командлеты и для получения сведений о импортированных командах. `Test-Files`Командлет был экспортирован с компьютера Server01 и добавлен в сеанс. `Test-Files`Командлет выполняется в удаленном сеансе на компьютере, с которого была импортирована команда. PowerShell создает сеанс на основе сведений, которые хранятся в модуле TestCmdlets.

### Пример 4. экспорт и затереть команд в текущем сеансе

В этом примере выполняется экспорт команд, хранимых в переменной, в текущий сеанс.

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

Эта `Export-PSSession` команда экспортирует все команды и данные форматирования из сеанса PSSession в переменной в `$S` текущий сеанс. Параметр **AllowClobber** включает команды с теми же именами, что и команды в текущем сеансе.

### Пример 5. экспорт команд из закрытого сеанса PSSession

В этом примере показано, как выполнить экспортированные команды с особыми параметрами, когда сеанс PSSession, создавший экспортированные команды, закрыт.

Если исходный удаленный сеанс закрывается при импорте модуля, модуль будет использовать любой открытый удаленный сеанс, который подключается к исходному компьютеру. Если на исходном компьютере нет текущего сеанса, модуль повторно установит сеанс.

Чтобы выполнить экспортированные команды с особыми параметрами в удаленном сеансе, необходимо создать удаленный сеанс с этими параметрами перед импортом модуля. Используйте `New-PSSession` командлет с параметром **SessionOption**

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

`New-PSSessionOption`Командлет создает объект **PSSessionOption** и сохраняет объект в `$Options` переменной. `New-PSSession`Команда создает сеанс PSSession на компьютере Server01.
Параметр **SessionOption** использует объект, хранящийся в `$Options` . Сеанс хранится в `$S` переменной.

`Export-PSSession`Командлет экспортирует команды из PSSession в в `$S` модуль Server01.
`Remove-PSSession`Командлет удаляет сеанс PSSession в `$S` переменной.

`New-PSSession`Командлет создает новый сеанс PSSession, который подключается к компьютеру Server01. Параметр **SessionOption** использует объект, хранящийся в `$Options` . `Import-Module`Командлет импортирует команды из модуля Server01. Команды в модуле запускаются в сеансе PSSession на компьютере Server01.

## PARAMETERS

### -AllowClobber

Экспортирует указанные команды, даже если их имена совпадают с именами команд в текущем сеансе.

При экспорте команды с тем же именем, что и у команды в текущем сеансе, экспортированная команда скрывает или заменяет исходные команды. Дополнительные сведения см. в разделе [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).

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

Экспортирует вариант команды, полученный с использованием заданных аргументов (значений параметров).

Например, чтобы экспортировать вариант `Get-Item` команды в сертификате (CERT:) диск в PSSession в `$S` введите `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .

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

Указывает сертификат клиента, используемый для подписи файлов форматирования (* .Format.ps1XML) или файлов модулей скриптов (. PSM1) в `Export-PSSession` создаваемом модуле. Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.

Чтобы найти сертификат, используйте `Get-PfxCertificate` командлет или используйте `Get-ChildItem` командлет в сертификате (CERT:). диск. Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.

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

Экспортирует только команды с указанными именами или шаблонами имен. Разрешено использовать подстановочные знаки. Используйте **CommandName** или его псевдоним, **имя**.

По умолчанию `Export-PSSession` экспортирует все команды из PSSession, за исключением команд, имена которых совпадают с именами команд в текущем сеансе. Это предотвращает скрытие и замену команд в текущем сеансе командами. Чтобы экспортировать все команды, даже те, которые скрывают или заменяют другие команды, используйте параметр **AllowClobber** .

При использовании параметра **CommandName** файлы форматирования для команд не экспортируются, если не используется параметр **FormatTypeName** . Аналогично, если используется параметр **FormatTypeName** , команды не экспортируются, если не используется параметр **CommandName** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: True
```

### -CommandType

Экспортирует только указанные типы объектов команд. Используйте параметр **CommandType** или его псевдоним **Type**.

Для этого параметра допустимы следующие значения:

- Псевдоним. Все псевдонимы PowerShell в текущем сеансе.
- Все. все типы команд. Он эквивалентен `Get-Command -Name *` .
- приложение. Все файлы, кроме файлов PowerShell, в путях, указанных в переменной среды PATH ( `$env:path` ), включая txt, exe и DLL-файлы.
- Командлет. командлеты в текущем сеансе. По умолчанию используется командлет.
- Настройка. Конфигурация PowerShell. Дополнительные сведения см. в разделе [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).
- Екстерналскрипт. Все PS1-файлы в путях, указанных в переменной среды PATH ( `$env:path` ).
- Фильтр и функция. Все функции PowerShell.
- Скрипт. блоки скриптов в текущем сеансе.
- Процессов. Рабочий процесс PowerShell. Дополнительные сведения см. в разделе [about_Workflows](/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1).

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, All, Application, Cmdlet, Configuration, ExternalScript, Filter, Function, Script, Workflow

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding

Указывает тип кодировки для целевого файла. Значение по умолчанию — `utf8NoBOM`.

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.


Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Перезаписывает один или несколько существующих выходных файлов, даже если для них задан атрибут "Только для чтения".

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

Экспортирует инструкции форматирования только для указанных типов Microsoft .NET Framework. Введите имена типов. По умолчанию `Export-PSSession` экспортирует инструкции по форматированию для всех типов .NET Framework, которые не входят в пространство имен **System. Management. Automation** .

Значение этого параметра должно быть именем типа, возвращаемого `Get-FormatData` командой в сеансе, из которого импортируются команды. Чтобы получить все данные форматирования в удаленном сеансе, введите `*` .

Если используется параметр **FormatTypeName** , команды не экспортируются, если не используется параметр **CommandName** .

При использовании параметра **CommandName** файлы форматирования для команд не экспортируются, если не используется параметр **FormatTypeName** .

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

Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .
См. раздел "Примечания" [конструктора ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290).

Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет. Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** ; два параметра являются взаимоисключающими.

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

Экспортирует только команды в указанных оснастках и модулях PowerShell. Введите имена оснасток и модулей. Использовать подстановочные знаки запрещено.

Дополнительные сведения см. в статьях `Import-Module` и [about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### -Аутпутмодуле

Указывает необязательный путь и имя для модуля, созданного `Export-PSSession` . Путь по умолчанию: `$home\Documents\WindowsPowerShell\Modules`. Этот параметр обязателен.

Если подкаталог модуля или любой из создаваемых файлов `Export-PSSession` уже существует, команда завершается ошибкой. Чтобы перезаписать существующие файлы, используйте параметр **Force** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, ModuleName

Required: True
Position: 1
Default value: $home\Documents\WindowsPowerShell\Modules
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Указывает сеанс PSSession, из которого экспортируются команды. Введите переменную, содержащую объект сеанса, или команду, которая получает объект сеанса, например `Get-PSSession` команду. Этот параметр обязателен.

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

Вы не можете передать объекты в `Export-PSSession` .

## Выходные данные

### System. IO. FileInfo

`Export-PSSession` Возвращает список файлов, составляющих созданный им модуль.

## ПРИМЕЧАНИЯ

`Export-PSSession` полагается на инфраструктуру удаленного взаимодействия PowerShell. Для использования этого командлета компьютер должен быть настроен для удаленного взаимодействия. Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Нельзя использовать `Export-PSSession` для экспорта поставщика PowerShell.

Экспортируемые команды выполняются неявно в сеансе PSSession, из которого они были экспортированы. Сведения об удаленном выполнении команд полностью обрабатываются PowerShell. Экспортируемые команды можно выполнять так же, как и локальные.

`Export-ModuleMember` захватывает и сохраняет сведения о PSSession в экспортируемом модуле. Если сеанс PSSession, из которого экспортированы команды, закрывается при импорте модуля и отсутствуют активные PSSession на том же компьютере, команды в модуле пытаются повторно создать PSSession. Если попытка повторно создать сеанс PSSession завершится ошибкой, экспортированные команды не будут выполняться.

Сведения о сеансе, которые `Export-ModuleMember` регистрируются и сохраняются в модуле, не включают параметры сеанса, такие как указанные в `$PSSessionOption` переменной предпочтений или с помощью параметра **SessionOption** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, или. Если при импорте модуля исходный сеанс PSSession закрыт, модуль будет использовать другой сеанс PSSession на том же компьютере, если такой доступен. Чтобы импортированные команды могли выполняться в правильно настроенном сеансе, создайте сеанс PSSession с нужными параметрами перед импортом модуля.

Чтобы найти команды для экспорта, `Export-PSSession` использует `Invoke-Command` командлет для выполнения `Get-Command` команды в PSSession. Чтобы получить и сохранить данные форматирования для команд, используются `Get-FormatData` `Export-FormatData` командлеты и. При выполнении команды могут отображаться сообщения об ошибках `Invoke-Command` , `Get-Command` , `Get-FormatData` и `Export-FormatData` `Export-PSSession` . Кроме того, `Export-PSSession` не может экспортировать команды из сеанса, не включающего `Get-Command` `Get-FormatData` командлеты,, `Select-Object` и `Get-Help` .

`Export-PSSession``Write-Progress`отображает ход выполнения команды с помощью командлета. Во время выполнения команды может отображаться индикатор выполнения .

К экспортированным командам применяются те же ограничения, что и к другим удаленным командам, включая невозможность запустить программу с пользовательским интерфейсом, например Блокнот.

Так как профили PowerShell не выполняются в PSSession, команды, которые профиль добавляет в сеанс, недоступны `Export-PSSession` . Чтобы экспортировать команды из профиля, используйте `Invoke-Command` команду для запуска профиля в сеансе PSSession вручную перед экспортом команд.

`Export-PSSession`Создаваемый модуль может включать файл форматирования, даже если команда не импортирует данные форматирования. Если команда не импортирует данные форматирования, все создаваемые файлы форматирования не будут содержать данные форматирования.

## Связанные ссылки

[about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[about_PSSessions](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1)

[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[Import-Module](../Microsoft.PowerShell.Core/Import-Module.md)

[Import-PSSession](Import-PSSession.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-PSSessionOption](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[Remove-PSSession](../Microsoft.PowerShell.Core/Remove-PSSession.md)
