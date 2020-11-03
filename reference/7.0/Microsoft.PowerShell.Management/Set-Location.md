---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: dddc3d8309095520167d80ac73bb45399ba436f5
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "93230438"
---
# Set-Location

## Краткий обзор
Присваивает текущему рабочему расположению указанное значение.

## SYNTAX

### Путь (по умолчанию)

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### LiteralPath

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### Стек

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## DESCRIPTION

`Set-Location`Командлет задает рабочее расположение в указанном расположении. Это расположение может быть каталогом, подкаталогом, расположением реестра или любым путем к поставщику.

В PowerShell 6,2 добавлена поддержка `-` и `+` в качестве значений параметра **path** . PowerShell поддерживает журнал последних 20 расположений, к которым можно получить доступ с помощью `-` и `+` . Этот список не зависит от стека расположения, доступ к которому осуществляется с помощью параметра **StackName** .

## Примеры

### Пример 1. Задание текущего расположения

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

Эта команда устанавливает текущее расположение в корневую папку `HKLM:` диска.

### Пример 2. Настройка текущего расположения и отображение этого расположения

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

Эта команда устанавливает текущее расположение в корневую папку `Env:` диска. Он использует параметр **PassThru** , чтобы направить PowerShell для возврата объекта **PathInfo** , представляющего `Env:\` расположение.

### Пример 3. Задание расположения для текущего расположения на диске C:

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

Первая команда задает расположение в качестве корня `HKLM:` диска в поставщике реестра.
Вторая команда задает расположение текущего расположения `C:` диска в поставщике FileSystem.
Если имя диска указано в форме `<DriveName>:` (без обратной косой черты), командлет задает расположение в текущем расположении в PSDrive.
Чтобы получить текущее расположение в команде PSDrive use, выполните `Get-Location -PSDrive <DriveName>` команду.

### Пример 4. Установка текущего расположения в именованный стек

```
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

Первая команда добавляет текущее расположение в стек путей.
Вторая команда создает стек Locations Stack в текущем стеке расположения.
Третья команда отображает расположения в текущем стеке расположений.

`*-Location`Командлеты используют текущий стек расположения, если в команде не указан другой стек расположения. Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

### Пример 5. Навигация по журналу расположения с помощью `+` или `-`

```
PS C:\> Set-Location -Path $env:SystemRoot
PS C:\Windows> Set-Location -Path Cert:\
PS Cert:\> Set-Location -Path HKLM:\
PS HKLM:\>

# Navigate back through the history using "-"
PS HKLM:\> Set-Location -Path -
PS Cert:\> Set-Location -Path -
PS C:\Windows>

# Navigate using the Set-Location alias "cd" and the implicit positional Path parameter
PS C:\Windows> cd -
PS C:\> cd +
PS C:\Windows> cd +
PS Cert:\>
```

С помощью псевдонима `cd -` или `cd +` можно легко перемещаться по журналу расположения в терминале. Дополнительные сведения о переходе по см `-` / `+` . в разделе параметр **path** .

## PARAMETERS

### -LiteralPath

Указывает путь к расположению. Значение параметра **LiteralPath** используется точно так же, как оно введено. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект **PathInfo** , представляющий расположение. По умолчанию этот командлет не создает выходные данные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Укажите путь к новому рабочему расположению. Если путь не указан, `Set-Location` по умолчанию используется домашний каталог текущего пользователя. Если используются подстановочные знаки, командлет выбирает первый путь, соответствующий шаблону шаблона.

PowerShell сохраняет историю последних 20 заданных расположений. Если значение параметра **path** является `-` символом, новое рабочее расположение будет предыдущим рабочим расположением в журнале (если оно существует). Аналогично, если значение является `+` символом, новое рабочее расположение будет следующим рабочим расположением в журнале (если оно существует). Это похоже на использование `Pop-Location` и `Push-Location` за исключением того, что журнал является списком, а не стеком и неявно отслеживанием, а не управляется вручную. В настоящее время нет способа просмотреть список журналов.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StackName

Указывает существующее имя стека расположения, которое этот командлет делает текущим стеком расположения. Введите имя стека папок. Чтобы указать неименованный стек расположения по умолчанию, введите `$null` или пустую строку ( `""` ).

`*-Location`Командлеты действуют в текущем стеке, если не используется параметр **StackName** для указания другого стека. Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

```yaml
Type: System.String
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.

## Выходные данные

### Нет, System. Management. Automation. PathInfo, System. Management. Automation. Пасинфостакк

Этот командлет не создает никаких выходных данных, если не указан параметр **PassThru** . При использовании команды **PassThru** с **path** или **LiteralPath** создается объект **PathInfo** , представляющий новое расположение. Использование функции **PassThru** с **StackName** создает объект **пасинфостакк** , представляющий новый контекст стека.

## ПРИМЕЧАНИЯ

PowerShell поддерживает несколько пространств выполнения для каждого процесса. Каждое пространство выполнения имеет свой собственный _текущий каталог_ .
Это не то же самое, что `[System.Environment]::CurrentDirectory` . Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.

Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время. Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.

`Set-Location`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).

Стек — это последний список, в котором можно получить доступ только к последним добавленным элементам. Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке. PowerShell позволяет хранить расположения поставщиков в стеках расположений. PowerShell создает неименованный стек расположения по умолчанию. Можно создать несколько именованных стеков расположения. Если имя стека не указано, PowerShell использует текущий стек расположения. По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.

Для управления стеками расположений используйте `*-Location` командлеты следующим образом:

- Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.

- Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.

- Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета. Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** из `Get-Location` .

- Чтобы создать новый стек расположений, используйте параметр **StackName** из `Push-Location` . Если указан несуществующий стек, `Push-Location` создает стек.

- Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** из `Set-Location` .

Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.
Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке. Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$null` или пустой строкой ( `""` ).

## Связанные ссылки

[Get-Location](Get-Location.md)

[Pop-Location](Pop-Location.md)

[Push-Location](Push-Location.md)
