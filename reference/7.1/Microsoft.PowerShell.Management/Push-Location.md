---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: 91ee85507d8ad0f128025af3d549d461310a415d
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "93230241"
---
# Push-Location

## Краткий обзор
Добавляет текущее расположение в начало стека папок.

## SYNTAX

### Путь (по умолчанию)

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

### LiteralPath

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## DESCRIPTION

`Push-Location`Командлет добавляет ("отправляет") текущее расположение в стек расположений. Если указать путь, `Push-Location` передает текущее расположение в стек, а затем меняет текущее расположение на расположение, указанное в пути. `Pop-Location`Для получения расположений из стека расположений можно использовать командлет.

По умолчанию `Push-Location` командлет отправляет текущее расположение в стек текущего расположения, но можно использовать параметр **StackName** для указания альтернативного стека расположения. Если стек не существует, `Push-Location` создает его.

Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

## Примеры

### Пример 1

Этот пример отправляет текущее расположение в стек папок по умолчанию, а затем изменяет расположение на `C:\Windows` .

```
PS C:\> Push-Location C:\Windows
```

### Пример 2

Этот пример отправляет текущее расположение в стек Регфунктион и изменяет текущее расположение на `HKLM:\Software\Policies` расположение.

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

Командлеты Location можно использовать на любом диске PowerShell (PSDrive).

### Пример 3

Эта команда помещает текущее расположение в стек по умолчанию. Она не меняет расположение.

```
PS C:\> Push-Location
```

### Пример 4. Создание и использование именованного стека

Эти команды показывают, как создавать и использовать именованные стеки папок.

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

Первая команда помещает текущее расположение в новый стек с именем Stack2, а затем изменяет текущее расположение на корневой каталог, представленный в команде символом тильды ( `~` ), который при использовании на дисках поставщика файловой системы эквивалентен `$HOME` и `$env:USERPROFILE` .

Если Stack2 еще не существует в сеансе, `Push-Location` создает его. Вторая команда использует `Pop-Location` командлет для POP в исходное расположение ( `C:\` ) из стека Stack2. Без параметра **StackName** `Pop-Location` будет вытолкнуть расположение из неименованного стека по умолчанию.

Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

## PARAMETERS

### -LiteralPath

Указывает путь к новому расположению. В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Передает объект, представляющий расположение, по конвейеру. По умолчанию этот командлет не создает выходные данные.

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

Добавляет текущее расположение в начало стека и заменяет это расположение на указанное данным путем. Введите путь к любому расположению, поставщик которого поддерживает данный командлет. Разрешено использовать подстановочные знаки. Имя параметра является необязательным.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StackName

Указывает стек папок, в который будет добавлено текущее расположение. Введите имя стека папок.
Если стек не существует, `Push-Location` создает его.

Без этого параметра `Push-Location` добавляет расположение в текущий стек расположения. По умолчанию текущий стек расположений — это безымянный стек расположения по умолчанию, создаваемый PowerShell.
Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета. Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

> [!NOTE]
> `Push-Location` невозможно добавить расположение в неименованный стек по умолчанию, если он не является текущим стеком расположения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку, содержащую путь (но не литеральный путь), можно передать в `Push-Location` .

## Выходные данные

### None или System. Management. Automation. PathInfo

При использовании параметра **PassThru** `Push-Location` создает объект **System. Management. Automation. PathInfo** , представляющий расположение. В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

PowerShell поддерживает несколько пространств выполнения для каждого процесса. Каждое пространство выполнения имеет свой собственный _текущий каталог_ .
Это не то же самое, что `[System.Environment]::CurrentDirectory` . Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.

Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время. Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.

Стек — это последний список, в котором доступен только последний добавленный элемент.
Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке. PowerShell позволяет хранить расположения поставщиков в стеках расположений.

PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения. Если имя стека не указано, PowerShell использует текущий стек расположения. По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.

Для управления стеками расположений используйте командлеты расположения PowerShell, как показано ниже.

- Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.

- Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.

- Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.

- Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.

- Чтобы создать новый стек расположений, используйте параметр StackName `Push-Location` командлета. Если указан несуществующий стек, `Push-Location` создает стек.

- Чтобы сделать стек расположения текущим стеком расположения, используйте параметр StackName `Set-Location` командлета.

Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.
Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке. Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$null` или пустой строкой ( `""` ).

Также можно ссылаться `Push-Location` по встроенному псевдониму `pushd` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

`Push-Location`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Get-Location](Get-Location.md)

[Pop-Location](Pop-Location.md)

[Set-Location](Set-Location.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
