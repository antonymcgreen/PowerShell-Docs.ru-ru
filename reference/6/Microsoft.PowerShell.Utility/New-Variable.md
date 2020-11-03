---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: faf8bc399185da402bebb678b02927e0e5628662
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228698"
---
# New-Variable

## Краткий обзор
Создает новую переменную.

## SYNTAX

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **New-Variable** создает новую переменную в PowerShell.
Значение для переменной можно назначить при ее создании или изменив созданное значение.

Для задания свойств переменной, определения области видимости переменной и проверки того, являются ли переменные общедоступными или частными, можно использовать параметры **новой переменной** .

Как правило, Новая переменная создается путем ввода имени переменной и ее значения, например `$Var = 3` , но можно использовать командлет **New-Variable** , чтобы использовать его параметры.

## Примеры

### Пример 1. Создание переменной

```
PS C:\> New-Variable days
```

Эта команда создает новую переменную с именем Days.
Вам не нужно вводить параметр *Name* .

### Пример 2. Создание переменной и присвоение ей значения

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

Эта команда создает переменную с именем ZipCode и присваивает ей значение 98033.

### Пример 3. Создание переменной с параметром ReadOnly

```
PS C:\> New-Variable -Name Max -Value 256 -Option ReadOnly
PS C:\> New-Variable -Name max -Value 1024

New-Variable : A variable with name 'max' already exists.
At line:1 char:1
+ New-Variable -Name max -Value 1024
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (max:String) [New-Variable], SessionStateException
    + FullyQualifiedErrorId : VariableAlreadyExists,Microsoft.PowerShell.Commands.NewVariableCommand

PS C:\> New-Variable -Name max -Value 1024 -Force
```

В этом примере показано, как использовать параметр ReadOnly **переменной New-Variable** , чтобы защитить переменную от переписывания.

Первая команда создает новую переменную с именем Max и присваивает ей значение 256.
В нем используется параметр *Option* со значением ReadOnly.

Вторая команда пытается создать вторую переменную с таким же именем.
Эта команда возвращает ошибку, поскольку для переменной задан параметр "только для чтения".

Третья команда использует параметр *Force* , чтобы переопределить защиту только для чтения для переменной.
В этом случае команда создания новой переменной с тем же именем успешно выполняется.

### Пример 4. Создание закрытой переменной

```
PS C:\> New-Variable -Name counter -Visibility Private

#Effect of private variable in a module.

PS C:\> Get-Variable c*

Name                           Value
----                           -----
Culture                        en-US
ConsoleFileName
ConfirmPreference              High
CommandLineParameters          {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"
At line:1 char:1
+ $counter
+ ~~~~~~~~
    + CategoryInfo          : PermissionDenied: (counter:String) [], SessionStateException
    + FullyQualifiedErrorId : VariableIsPrivate

PS C:\> Get-Counter
Name         Value
----         -----
Counter1     3.1415
...
```

Эта команда демонстрирует поведение частной переменной в модуле.
Модуль содержит командлет Get-Counter, который имеет закрытую переменную с именем Counter.
Команда использует параметр *видимости* со значением Private, чтобы создать переменную.

В примере выходных данных показано поведение частной переменной.
Пользователь, загрузивший модуль, не может просматривать или изменять значение переменной Counter, но переменную Counter можно прочитать и изменить с помощью команд в модуле.

### Пример 5. Создание переменной с пробелом

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

Эта команда показывает, что можно создать переменные с пробелами.
Доступ к переменным можно получить с помощью командлета **Get-Variable** или напрямую, разделив переменную фигурными скобками.

## PARAMETERS

### -Description
Указывает описание переменной.

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

### -Force
Указывает, что командлет создает переменную с тем же именем, что и существующая переменная, доступная только для чтения.

По умолчанию переменную можно перезаписать, за исключением случаев, когда она имеет значение параметра ReadOnly или Constant.
Дополнительные сведения см. в описании параметра *Option* .

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

### -Name
Указывает имя новой переменной.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Параметр-Option
Задает значение свойства **Options** переменной. Допустимые значения для этого параметра:

- Отсутствует.
не определяет параметров
(Значение по умолчанию — None.)
- Доступно.
псевдоним можно удалить,
Нельзя изменить, за исключением использования параметра *Force* .
- Закрытый.
переменная доступна только в текущей области.
- AllScope.
переменная копируется в новые созданные области.
- Константа.
псевдоним нельзя удалить или изменить.
Константа допустима только при создании переменной.
Параметры существующей переменной нельзя изменить на константу.

Чтобы просмотреть свойство **Options** всех переменных в сеансе, введите `Get-Variable | Format-Table -Property name, options -autosize` .

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Возвращает объект, представляющий элемент, с которым вы работаете.
По умолчанию этот командлет не создает выходные данные.

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

### -Scope
Задает область новой переменной.
Допустимые значения для этого параметра:

- Глобального.
Переменные, созданные в глобальной области, доступны везде в процессе PowerShell.
- Локальный.
Локальная область ссылается на текущую область, это может быть любая область в зависимости от контекста.
- Скрипт.
Переменные, созданные в области скриптов, доступны только в файле скрипта или модуле, в котором они созданы.
- Закрытый.
К переменным, созданным в закрытой области, нельзя обращаться за пределами области, в которой они существуют.
Частную область можно использовать для создания закрытой версии элемента с тем же именем в другой области.
- Число относительно текущей области (от 0 до количества областей, где 0 является текущей областью, 1 — ее родителем, 2 родителя родительской области и т. д.).
Отрицательные числа использовать нельзя.

Значение Local является областью по умолчанию, если параметр области не указан.

Дополнительные сведения см. в разделе about_Scopes.

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

### -Value
Указывает первоначальное значение переменной.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### — Видимость
Определяет, видима ли переменная вне сеанса, в котором она была создана.
Этот параметр предназначен для использования в скриптах и командах, которые будут переданы другим пользователям.
Допустимые значения для этого параметра:

- Общедоступный.
переменная видима.
(Значение по умолчанию — Public.)
- Закрытый.
переменная невидима.

Если переменная частная, она не отображается в списках переменных, например возвращаемых командлетом Get-Variable, или в выходных данных для диска Variable:.
Команды чтения или изменения значения частной переменной возвращают ошибку.
Однако пользователь может выполнять команды, использующие частную переменную, если они были написаны в сеансе, в котором определена переменная.

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Object
Значение можно передать в командлет **New-Variable** .

## Выходные данные

### None или System. Management. Automation. PSVariable
При использовании параметра *PassThru* командлет **New-Variable** создает объект **System. Management. Automation. PSVariable** , представляющий новую переменную.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
