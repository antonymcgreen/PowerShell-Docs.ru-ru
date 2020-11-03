---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: 5968c51f04199d59d3514cdc85ba3f15d02475a4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227517"
---
# Set-PSBreakpoint

## Краткий обзор
Устанавливает точку останова на строке, команде или переменной.

## SYNTAX

### Строка (по умолчанию)

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### Get-Help

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### Переменная

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## DESCRIPTION

`Set-PSBreakpoint`Командлет задает точку останова в скрипте или в любой команде, выполняемой в текущем сеансе. Можно использовать `Set-PSBreakpoint` для установки точки останова перед выполнением сценария или выполнением команды или во время отладки, если остановлена в другой точке останова.

`Set-PSBreakpoint` невозможно установить точку останова на удаленном компьютере. Для отладки сценария на удаленном компьютере скопируйте сценарий на локальный компьютер, а затем выполните отладку локально.

Каждая `Set-PSBreakpoint` команда создает один из следующих трех типов точек останова:

- Точка останова в строке — задает точки останова в определенных координатах строки и столбца.
- Точка останова команды — задает точки останова для команд и функций.
- Точка останова — задает точки останова для переменных.

Точку останова можно задать в нескольких строках, командах или переменных в одной `Set-PSBreakpoint` команде, но каждая `Set-PSBreakpoint` команда устанавливает только один тип точки останова.

В точке останова PowerShell временно останавливает выполнение и передает управление отладчику. Командная строка изменится на `DBG\>` , а набор команд отладчика станет доступным для использования. Однако можно использовать параметр **Action** , чтобы указать альтернативный ответ, например условия для точки останова или инструкции для выполнения дополнительных задач, таких как ведение журнала или диагностика.

`Set-PSBreakpoint`Командлет — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.
Дополнительные сведения о отладчике PowerShell см. в разделе [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).

## Примеры

### Пример 1. Задание точки останова в строке

В этом примере задается точка останова в строке 5 в скрипте Sample.ps1. При выполнении скрипта выполнение останавливается непосредственно перед выполнением строки 5.

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Line 5
```

```output
Column     : 0
Line       : 5
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

При установке новой точки останова по номеру строки `Set-PSBreakpoint` командлет создает объект точки останова строки ( **System. Management. Automation. линебреакпоинт** ), включающий идентификатор точки останова и число попаданий.

### Пример 2. Установка точки останова в функции

В этом примере создается точка останова команды для `Increment` функции в командлете Sample.ps1. Сценарий останавливает выполнение непосредственно перед каждым вызовом указанной функции.

```powershell
Set-PSBreakpoint -Command "Increment" -Script "sample.ps1"
```

```Output
Command    : Increment
Action     :
Enabled    : True
HitCount   : 0
Id         : 1
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

Результатом является объект точки останова команды. Перед выполнением скрипта значение свойства **хиткаунт** равно 0.

### Пример 3. Установка точки останова в переменной

В этом примере задается точка останова на **серверной** переменной в скрипте Sample.ps1. Он использует параметр **mode** со значением **ReadWrite** , чтобы прерывать выполнение при считывании значения переменной и непосредственно перед изменением значения.

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### Пример 4. Установка точки останова для каждой команды, которая начинается с указанного текста

В этом примере задается точка останова для каждой команды в Sample.ps1 скрипте, которая начинается с "Write", например `Write-Host` .

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### Пример 5. Задание точки останова в зависимости от значения переменной

В этом примере выполнение `DiskTest` функции в скрипте Test.ps1 прекращается, только если значение `$Disk` переменной больше 2.

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

Значением **действия** является блок скрипта, который проверяет значение `$Disk` переменной в функции.

Действие использует `break` ключевое слово для отмены выполнения при соблюдении условия. Альтернативный вариант (и значение по умолчанию) будет **продолжен** .

### Пример 6. Установка точки останова в функции

В этом примере задается точка останова для `CheckLog` функции. Поскольку команда не указывает сценарий, точка останова устанавливается для любого объекта, который выполняется в текущем сеансе. Отладчик останавливается при вызове функции, а не при ее объявлении.

```
PS> Set-PSBreakpoint -Command "checklog"
Id       : 0
Command  : checklog
Enabled  : True
HitCount : 0
Action   :

function CheckLog {
>> get-eventlog -log Application |
>> where {($_.source -like "TestApp") -and ($_.Message -like "*failed*")}
>>}
>>
PS> Checklog
DEBUG: Hit breakpoint(s)
DEBUG:  Function breakpoint on 'prompt:Checklog'
```

### Пример 7. Установка точек останова в нескольких строках

В этом примере задаются три точки останова по строке в скрипте Sample.ps1. Она задает одну точку останова в столбце 2 каждой из строк, указанных в сценарии. Действие, указанное в параметре **Action** , применяется ко всем точкам останова.

```powershell
PS C:\> Set-PSBreakpoint -Script "sample.ps1" -Line 1, 14, 19 -Column 2 -Action {&(log.ps1)}
```

```Output
Column     : 2
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 6
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 14
Action     :
Enabled    : True
HitCount   : 0
Id         : 7
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 19
Action     :
Enabled    : True
HitCount   : 0
Id         : 8
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

## PARAMETERS

### -Action

Задает команды, которые выполняются в каждой точке останова вместо останова. Введите блок сценария, содержащий команды. Этот параметр можно использовать для задания условных точек останова или выполнения других задач, таких как тестирование или ведение журнала.

Если этот параметр пропущен или не указаны никакие действия, выполнение останавливается в точке останова и запускается отладчик.

При использовании параметра **Action** блок сценария действия выполняется в каждой точке останова. Выполнение не останавливается, если блок сценария не включает ключевое слово Break. При использовании ключевого слова Continue в блоке сценария выполнение возобновляется до следующей точки останова.

Дополнительные сведения см. в разделе [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)и [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Column

Указывает номер столбца в файле сценария, в котором выполнение останавливается. Введите только один номер столбца. Значение по умолчанию: столбец 1.

Значение столбца используется со значением параметра **line** для указания точки останова. Если параметр **line** задает несколько строк, параметр **Column** задает точку останова в указанном столбце для каждой из указанных строк. PowerShell прекращает выполнение до инструкции или выражения, включающего символ в указанной строке и позиции столбца.

Столбцы отсчитываются от верхней левой границы, начиная с номера столбца 1 (не 0). Если указать столбец, который не существует в сценарии, ошибка не объявляется, однако точка останова не выполняется.

```yaml
Type: System.Int32
Parameter Sets: Line
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Задает точку останова команды. Введите имена командлетов, например `Get-Process` , или имена функций. Разрешено использовать подстановочные знаки.

Выполнение останавливается непосредственно перед выполнением каждого экземпляра каждой команды. Если команда является функцией, выполнение останавливается при каждом вызове функции и в каждом разделе BEGIN, PROCESS и END.

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases: C

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Line

Задает точку останова строки в сценарии. Введите один или несколько номеров строк, разделенных запятыми. PowerShell останавливается сразу перед выполнением инструкции, которая начинается на каждой из указанных строк.

Строки отсчитываются от верхней левой границы файла сценария, начиная с номера строки 1 (не 0).
Если указать пустую строку, выполнение останавливается перед следующей непустой строкой. Если строка выходит за пределы диапазона, останов не выполняется.

```yaml
Type: System.Int32[]
Parameter Sets: Line
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode

Задает режим доступа, который активирует переменные точки останова. Значение по умолчанию — **Write** .

Этот параметр допустим только в том случае, если в команде используется параметр **variable** . Режим применяется ко всем точкам останова, заданным в команде. Допустимые значения для этого параметра:

- **Запись** — останавливает выполнение непосредственно перед записью нового значения в переменную.
- **Чтение** — остановка выполнения при считывании переменной, то есть при доступе к ее значению, назначению, отображению или использования. В режиме чтения выполнение не прекращается при изменении значения переменной.
- **ReadWrite** — останавливает выполнение, когда переменная считывается или записывается.

```yaml
Type: System.Management.Automation.VariableAccessMode
Parameter Sets: Variable
Aliases:
Accepted values: Read, Write, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Script

Указывает массив файлов скрипта, в котором этот командлет задает точку останова. Введите пути и имена одного или нескольких файлов сценариев. Если файлы находятся в текущем каталоге, путь можно опустить.
Разрешено использовать подстановочные знаки.

По умолчанию точки останова переменной и точки останова команды задаются в любых командах, которые выполняются в текущем сеансе. Этот параметр является обязательным, только если задается точка останова строки.

```yaml
Type: System.String[]
Parameter Sets: Line, Command, Variable
Aliases:

Required: True (Line), False (Command, Variable)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Задает массив переменных, на которых этот командлет задает точки останова. Введите разделенный запятыми список переменных без знака доллара ( `$` ).

Используйте параметр **mode** для определения режима доступа, запускающего точки останова. Режим по умолчанию, Write, останавливает выполнение непосредственно перед записью нового значения в переменную.

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases: V

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Вы не можете передать входные данные в `Set-PSBreakpoint` .

## Выходные данные

### Объект точки останова (System. Management. Automation. Линебреакпоинт, System. Management. Automation. Вариаблебреакпоинт, System. Management. Automation. Коммандбреакпоинт)

`Set-PSBreakpoint` Возвращает объект, представляющий каждую точку останова, которую он задает.

## ПРИМЕЧАНИЯ

- `Set-PSBreakpoint` невозможно установить точку останова на удаленном компьютере. Для отладки сценария на удаленном компьютере скопируйте сценарий на локальный компьютер, а затем выполните отладку локально.
- При установке точки останова более чем в одной строке, команде или переменной `Set-PSBreakpoint` создает объект точки останова для каждой записи.
- При задании точки останова в функции или переменной в командной строке можно задать точку останова до или после создания функции или переменной.

## Связанные ссылки

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)
