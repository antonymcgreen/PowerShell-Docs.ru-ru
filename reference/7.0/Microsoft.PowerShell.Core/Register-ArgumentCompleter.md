---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: 0e0b5fcd99372d699bd6250383adc85b3a5f8847
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225945"
---
# Register-ArgumentCompleter

## Краткий обзор

Регистрирует пользовательский аргумент для завершения.

## SYNTAX

### Собственный

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### PowerShell

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## DESCRIPTION

`Register-ArgumentCompleter`Командлет регистрирует пользовательский аргумент Complete. Завершение аргумента позволяет обеспечить динамическое завершение табуляции во время выполнения любой указанной команды.

## Примеры

### Пример 1. Регистрация пользовательского аргумента Complete

В следующем примере выполняется регистрация завершения аргумента для параметра **ID** `Set-TimeZone` командлета.

```powershell
$scriptBlock = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)

    (Get-TimeZone -ListAvailable).Id | Where-Object {
        $_ -like "$wordToComplete*"
    } | ForEach-Object {
          "'$_'"
    }
}
Register-ArgumentCompleter -CommandName Set-TimeZone -ParameterName Id -ScriptBlock $scriptBlock
```

Первая команда создает блок скрипта, который принимает обязательные параметры, которые передаются при нажатии клавиши <kbd>Tab</kbd>пользователем. Дополнительные сведения см. в описании параметра **ScriptBlock** .

В блоке скрипта доступные значения для **идентификатора** извлекаются с помощью `Get-TimeZone` командлета. Свойство **ID** для каждого часового пояса передается в `Where-Object` командлет. `Where-Object`Командлет фильтрует все идентификаторы, которые не начинаются со значения, предоставленного параметром `$wordToComplete` , который представляет текст, введенный пользователем до нажатия клавиши <kbd>Tab</kbd>. Отфильтрованные идентификаторы передаются в `For-EachObject` командлет, который заключает каждое значение в кавычки, если значение содержит пробелы.

Вторая команда регистрирует завершенный аргумент, передавая ScriptBlock, **идентификатор** **ParameterName** и **CommandName** `Set-TimeZone` .

### Пример 2. Добавление сведений к значениям заполнения нажатием клавиши TAB

Следующий пример перезаписывает заполнение клавиши TAB для параметра **Name** `Stop-Service` командлета и возвращает только выполняющиеся службы.

```powershell
$s = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)
    $services = Get-Service | Where-Object {$_.Status -eq "Running" -and $_.Name -like "$wordToComplete*"}
    $services | ForEach-Object {
        New-Object -Type System.Management.Automation.CompletionResult -ArgumentList $_.Name,
            $_.Name,
            "ParameterValue",
            $_.Name
    }
}
Register-ArgumentCompleter -CommandName Stop-Service -ParameterName Name -ScriptBlock $s
```

Первая команда создает блок скрипта, который принимает обязательные параметры, которые передаются при нажатии клавиши <kbd>Tab</kbd>пользователем. Дополнительные сведения см. в описании параметра **ScriptBlock** .

В блоке скрипта первая команда извлекает все работающие службы с помощью `Where-Object` командлета. Службы передаются в `ForEach-Object` командлет. `ForEach-Object`Командлет создает новый объект [System. Management. Automation. комплетионресулт](/dotnet/api/system.management.automation.completionresult) и заполняет его именем текущей службы (представленной переменной конвейера `$_.Name` ).

Объект **комплетионресулт** позволяет предоставить дополнительные сведения для каждого возвращаемого значения:

- **комплетионтекст** (строка) — текст, используемый в качестве результата автоматического завершения. Это значение, отправляемое команде.
- **листитемтекст** (строка) — текст, отображаемый в списке, например, когда пользователь нажимает клавишу <kbd>CTRL</kbd> + <kbd>пробел</kbd>. Используется только для вывода и не передается команде, если она выбрана.
- **resultType** ( [комплетионресулттипе](/dotnet/api/system.management.automation.completionresulttype)) — тип результата завершения.
- **ToolTip** (строка) — текст подсказки с подробными сведениями о объекте.
  Это видно, когда пользователь выбирает элемент после нажатия клавиши <kbd>CTRL</kbd> + <kbd>Space</kbd>.

Последняя команда показывает, что остановленные службы по-прежнему могут передаваться в `Stop-Service` командлет вручную. Заполнение нажатием клавиши Tab является единственным аспектом.

### Пример 3. Регистрация собственного собственного аргумента Complete

Можно использовать **собственный** параметр, чтобы обеспечить завершение клавиши TAB для собственной команды. В следующем примере показано добавление заполнения клавишей TAB для `dotnet` интерфейса командной строки (CLI).

> [!NOTE]
> `dotnet complete`Команда доступна только в версии 2,0 и более поздних версиях CLI DotNet.

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

Первая команда создает блок скрипта, который принимает обязательные параметры, которые передаются при нажатии клавиши <kbd>Tab</kbd>пользователем. Дополнительные сведения см. в описании параметра **ScriptBlock** .

В блоке скрипта `dotnet complete` команда используется для выполнения заполнения нажатием клавиши TAB.
Результаты передаются в `ForEach-Object` командлет, который использует **Новый** статический метод класса [System. Management. Automation. комплетионресулт](/dotnet/api/system.management.automation.completionresult) для создания нового объекта **комплетионресулт** для каждого значения.

## PARAMETERS

### -CommandName

Задает имя команд в виде массива.

```yaml
Type: System.String[]
Parameter Sets: NativeSet, PowerShellSet
Aliases:

Required: True (NativeSet), False (PowerShellSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Native

Указывает, что завершение аргумента предназначено для собственной команды, где PowerShell не может завершить имена параметров.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NativeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterName

Указывает имя параметра, аргумент которого завершается. Указанное имя параметра не может быть перечислимым значением, например параметром **ForegroundColor** `Write-Host` командлета.

Дополнительные сведения о перечислениях см. в разделе [about_Enum](./About/about_Enum.md).

```yaml
Type: System.String
Parameter Sets: PowerShellSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Задает команды, выполняемые для выполнения заполнения нажатием клавиши TAB. Предоставленный блок скрипта должен возвращать значения, которые завершают входные данные. Блок скрипта должен выполнять девращение значений с помощью конвейера ( `ForEach-Object` , `Where-Object` и т. д.) или другого подходящего метода. Возврат массива значений приводит к тому, что PowerShell обрабатывает весь массив как **одно** значение заполнения Tab.

Блок скрипта должен принимать следующие параметры в указанном ниже порядке. Имена параметров не важны, так как PowerShell передает значения по положению.

- `$commandName` (Расположение 0) — Этот параметр задает имя команды, для которой блок скрипта обеспечивает заполнение нажатием клавиши TAB.
- `$parameterName` (Расположение 1) — Этот параметр задан для параметра, значение которого требует заполнения нажатием клавиши TAB.
- `$wordToComplete` (Расположение 2) — Этот параметр имеет значение, указанное пользователем до нажатия клавиши <kbd>Tab</kbd>. Блок скрипта должен использовать это значение для определения значений заполнения клавиши TAB.
- `$commandAst` (Расположение 3) — Этот параметр имеет значение дерево абстрактного синтаксиса (AST) для текущей входной строки. Дополнительные сведения см. в разделе [класс AST](/dotnet/api/system.management.automation.language.ast).
- `$fakeBoundParameters` (Расположение 4) — для этого параметра задается хэш-таблица `$PSBoundParameters` , содержащая для командлета перед нажатием пользователем <kbd>вкладки</kbd>. Дополнительные сведения см. в разделе [about_Automatic_Variables](./About/about_Automatic_Variables.md).

При указании **собственного** параметра блок скрипта должен принимать следующие параметры в указанном порядке. Имена параметров не важны, так как PowerShell передает значения по положению.

- `$wordToComplete` (Расположение 0) — Этот параметр имеет значение, указанное пользователем до нажатия клавиши <kbd>Tab</kbd>. Блок скрипта должен использовать это значение для определения значений заполнения клавиши TAB.
- `$commandAst` (Расположение 1) — Этот параметр имеет значение дерево абстрактного синтаксиса (AST) для текущей входной строки. Дополнительные сведения см. в разделе [класс AST](/dotnet/api/system.management.automation.language.ast).
- `$cursorPosition` (Расположение 2) — Этот параметр задает позицию курсора при нажатии пользователем <kbd>вкладки</kbd>.

В качестве атрибута параметра можно также указать **аргументкомплетер** . Дополнительные сведения см. в разделе [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).

## Входные данные

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### Нет

Этот командлет не возвращает выходные данные.

## ПРИМЕЧАНИЯ

## Связанные ссылки
