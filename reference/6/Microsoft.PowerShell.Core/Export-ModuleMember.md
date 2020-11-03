---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: ed08e68279b436ea5a3c040729d70990700ebdfa
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229285"
---
# Export-ModuleMember

## Краткий обзор
Задает элементы модуля, доступные для экспорта.

## SYNTAX

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Командлет **Export-ModuleMember** указывает элементы модуля, которые экспортируются из файла модуля скрипта (. PSM1), или из динамического модуля, созданного с помощью командлета New-Module.
К членам модуля относятся командлеты, функции, переменные и псевдонимы.
Этот командлет может использоваться только в файле модуля скрипта или в динамическом модуле.

Если модуль скрипта не содержит команду **Export-ModuleMember** , то функции и псевдонимы в модуле скрипта экспортируются, а переменные — нет.
Если модуль скрипта содержит команды **Export-ModuleMember** , экспортируются только элементы, указанные в командах **Export-ModuleMember** .
Можно также использовать **Export-ModuleMember** для подавления или экспорта элементов, импортируемых модулем скрипта из других модулей.

Команда **Export-ModuleMember** является необязательной, но рекомендуется.
Даже если команда подтверждает значения по умолчанию, она демонстрирует намерения автора модуля.

## Примеры

### Пример 1. Экспорт функций и псевдонимов в модуль скрипта

```powershell
Export-ModuleMember -Function * -Alias *
```

Эта команда экспортирует все функции и псевдонимы, определенные в модуле скрипта.

### Пример 2. экспорт специальных псевдонимов и функций

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

Эта команда экспортирует три псевдонима и три функции, определенные в модуле скрипта.

Формат этой команды позволяет указать имена элементов модуля.

### Пример 3. экспорт без элементов

```powershell
Export-ModuleMember
```

Эта команда указывает, что экспорт элементов, определенных в модуле скрипта, запрещен.

Она запрещает экспорт элементов модуля, но не скрывает элементы.
Пользователи могут читать и копировать элементы модуля и использовать оператор вызова (&) для обращения к неэкспортируемым элементам модуля.

### Пример 4. экспорт определенной переменной

```powershell
Export-ModuleMember -Variable increment
```

Эта команда экспортирует из модуля скрипта только переменную $increment.
Остальные элементы не экспортируются.

Если вы хотите экспортировать переменную, помимо экспорта функций в модуль, команда **Export-ModuleMember** должна включать имена всех функций и имя переменной.

### Пример 5. несколько команд экспорта

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

Эти команды показывают, как несколько команд **Export-ModuleMember** интерпретируется в файле модуля скрипта (. PSM1).

Они создают три функции и один псевдоним, а затем экспортируют две функции и псевдоним.

Без команд **Export-ModuleMember** все три функции и псевдоним будут экспортированы.
При использовании команд **Export-ModuleMember** экспортируются только функции **New-Test** и **Start-Test** , а также псевдоним самонастраивающихся пороговых значений.

### Пример 6. Экспорт элементов в динамический модуль

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

Эта команда показывает, как использовать Export-ModuleMember в динамическом модуле, созданном с помощью командлета **New-Module** .

В этом примере **Export-ModuleMember** используется для экспорта псевдонима Hi и функции **sayHello** в динамическом модуле.

### Пример 7. объявление и экспорт функции в одной команде

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

В этом примере содержится функция с именем **Export** , которая объявляет функцию или создает переменную, а затем записывает `Export-ModuleMember` команду для функции или переменной.
Это позволяет объявлять и экспортировать функцию или переменную в одной команде.

Чтобы использовать функцию **экспорта** , включите ее в модуль скрипта.
Чтобы экспортировать функцию, введите `Export` перед ключевым словом **Function** .

Чтобы экспортировать переменную, используйте следующий формат для объявления переменной и задания ее значения:

`Export variable <variable-name> <value>`

В примере показан правильный формат команд.
В этом примере экспортируются только функция **New-Test** и переменная $Interval.

## PARAMETERS

### -Alias

Задает псевдонимы, экспортируемые из файла модуля скрипта.
Введите имена псевдонимов.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Командлет

Задает командлеты, экспортируемые из файла модуля скрипта.
Введите имена командлетов.
Можно использовать подстановочные знаки.

В файле модуля скрипта нельзя создавать командлеты, однако, их можно импортировать из двоичного модуля в модуль скрипта и экспортировать из модуля скрипта.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Function

Задает функции, экспортируемые из файла модуля скрипта.
Введите имена функций.
Можно использовать подстановочные знаки.
Вы также можете передать строки имени функции в **Export-ModuleMember**.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Variable

Задает переменные, экспортируемые из файла модуля скрипта.
Введите имена переменных без знака доллара.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

В этот командлет можно передать строки имени функции.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Чтобы исключить член из списка экспортируемых элементов, добавьте команду **Export-ModuleMember** , которая перечисляет все остальные элементы, но не включает элемент, который требуется исключить.

## Связанные ссылки

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[Remove-Module](Remove-Module.md)
