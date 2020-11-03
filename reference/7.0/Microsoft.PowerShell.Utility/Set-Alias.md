---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 2/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 86eff41bc9784627db82689108d01cbd71840e77
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225626"
---
# Set-Alias

## Краткий обзор
Создает или изменяет псевдоним для командлета или другой команды в текущем сеансе PowerShell.

## SYNTAX

### Default (по умолчанию)

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Alias`Командлет создает или изменяет псевдоним для командлета или команды, например функции, скрипта, файла или другого исполняемого файла. Псевдоним — это альтернативное имя, которое ссылается на командлет или команду.
Например, `sal` является псевдонимом для `Set-Alias` командлета. Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Командлет может иметь несколько псевдонимов, но псевдоним может быть связан только с одним командлетом. Можно использовать для повторного `Set-Alias` назначения существующего псевдонима другому командлету или для изменения свойств псевдонима, таких как описание.

Псевдоним, созданный или измененный, `Set-Alias` не является постоянным и доступен только во время текущего сеанса PowerShell. При закрытии сеанса PowerShell псевдоним удаляется.

## Примеры

### Пример 1. Создание псевдонима для командлета

Эта команда создает псевдоним для командлета в текущем сеансе PowerShell.

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell. Параметр **Name** задает имя псевдонима, `list` . Параметр **value** указывает командлет, который выполняется псевдонимом.

Чтобы запустить псевдоним, введите `list` в командной строке PowerShell.

### Пример 2. повторное назначение существующего псевдонима другому командлету

Эта команда переназначает существующий псевдоним для выполнения другого командлета.

```
PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem

PS> Set-Alias -Name list -Value Get-Location

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-Location
```

`Get-Alias`Командлет использует параметр **Name** для вывода `list` псевдонима. `list`Псевдоним связан с `Get-ChildItem` командлетом. При `list` запуске псевдонима отображаются элементы в текущем каталоге.

`Set-Alias`Командлет использует параметр **Name** для указания `list` псевдонима. Параметр **value** связывает псевдоним с `Get-Location` командлетом.

`Get-Alias`Командлет использует параметр **Name** для вывода `list` псевдонима. `list`Псевдоним связан с `Get-Location` командлетом. При `list` запуске псевдонима отображается расположение текущего каталога.

### Пример 3. Создание и изменение псевдонима, доступного только для чтения

Эта команда создает псевдоним только для чтения. Параметр только для чтения предотвращает непреднамеренное изменение псевдонима. Чтобы изменить или удалить псевдоним только для чтения, используйте параметр **Force** .

```
PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         :
Name                : loc
CommandType         : Alias

PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -Description 'Displays the current directory' -Force -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         : Displays the current directory
Name                : loc
CommandType         : Alias
```

`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell. Параметр **Name** задает имя псевдонима, `loc` . Параметр **value** указывает `Get-Location` командлет, который выполняется псевдонимом. Параметр **Option** задает значение **ReadOnly** . Параметр **PassThru** представляет объект Alias и отправляет объект по конвейеру в `Format-List` командлет. `Format-List` использует параметр **Property** со звездочкой ( `*` ), чтобы отображались все свойства. В примере выходных данных показан частичный список этих свойств.

`loc`Псевдоним изменяется с добавлением двух параметров. **Описание** добавляет текст для объяснения назначения псевдонима. Параметр **Force** необходим, так как `loc` псевдоним доступен только для чтения. Если параметр **Force** не используется, изменение завершается ошибкой.

### Пример 4. Создание псевдонима для исполняемого файла

В этом примере создается псевдоним для исполняемого файла на локальном компьютере.

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell. Параметр **Name** задает имя псевдонима, `np` . Параметр **value** задает путь и имя приложения **C:\Windows\notepad.exe** . `Get-Alias`Командлет использует параметр **Name** , чтобы отобразить `np` псевдоним, связанный с **notepad.exe** .

Чтобы запустить псевдоним, введите `np` команду в командной строке PowerShell, чтобы открыть **notepad.exe** .

### Пример 5. Создание псевдонима для команды с параметрами

В этом примере показано, как назначить псевдоним команде с параметрами.

Можно создать псевдоним для командлета, например `Set-Location` . Нельзя создать псевдоним для команды с параметрами и значениями, такими как `Set-Location -Path C:\Windows\System32` . Чтобы создать псевдоним для команды, создайте функцию, которая содержит команду, а затем создайте псевдоним для функции. Дополнительные сведения см. в разделе [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

Создается функция с именем `CD32` . Функция использует `Set-Location` командлет с параметром **path** для указания каталога **C:\Windows\System32** .

`Set-Alias`Командлет создает псевдоним для функции в текущем сеансе PowerShell. Параметр **Name** задает имя псевдонима, `Go` . Параметр **value** задает имя функции, `CD32` .

Чтобы запустить псевдоним, введите `Go` в командной строке PowerShell. `CD32`Функция выполняется и изменяется в каталоге **C:\Windows\System32** .

## PARAMETERS

### -Description

Указывает описание псевдонима. Можно ввести любую строку. Если описание содержит пробелы, заключите его в одинарные кавычки.

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

Используйте параметр **Force** для изменения или удаления псевдонима, у которого параметр **Option** установлен в значение **ReadOnly** .

Параметр **Force** не может изменить или удалить псевдоним **с параметром параметра,** установленным в значение **Constant** .

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

### -Name

Задает имя нового псевдонима. Имя псевдонима может содержать буквенно-цифровые символы и дефисы. Имена псевдонимов не могут быть числовыми, например 123.

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

Задает значение свойства **параметра** для псевдонима. Такие значения, как **ReadOnly** и **Constant** , защищают псевдоним от непреднамеренного изменения. Чтобы просмотреть свойство **параметра** всех псевдонимов в сеансе, введите `Get-Alias | Format-Table -Property Name, Options -Autosize` .

Для этого параметра допустимы следующие значения:

- **AllScope** Псевдоним копируется во все новые создаваемые области.
- **Константа** Нельзя изменить или удалить.
- **Нет** Задает параметры без параметров и является значением по умолчанию.
- **Частный** Псевдоним доступен только в текущей области.
- **Только для чтения** Нельзя изменить или удалить, если не используется параметр **Force** .
- **Unspecified**

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: AllScope, Constant, None, Private, ReadOnly, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий псевдоним. Используйте командлет Format, например, `Format-List` для вывода объекта. По умолчанию не `Set-Alias` создает никаких выходных данных.

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

Задает область действия псевдонима. Значение по умолчанию — **Local** . Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

Допустимы следующие значения:

- Глобальный
- Локальная
- Private
- Пронумерованные области
- Сценарий

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Global, Local, Private, Numbered scopes, Script

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Указывает имя командлета или команды, которую выполняет псевдоним. Параметр **value** является свойством **определения** псевдонима.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

### Нет

`Set-Alias` не принимает входные данные из конвейера.

## Выходные данные

### None или System. Management. Automation. AliasInfo

При использовании параметра **PassThru** `Set-Alias` создает объект **System. Management. Automation. AliasInfo** , представляющий псевдоним. В противном случае не `Set-Alias` создает никаких выходных данных.

## ПРИМЕЧАНИЯ

PowerShell включает встроенные псевдонимы, доступные в каждом сеансе PowerShell. `Get-Alias`Командлет отображает псевдонимы, доступные в сеансе PowerShell.

Чтобы создать псевдоним, используйте командлеты `Set-Alias` или `New-Alias` . Чтобы удалить псевдоним в PowerShell 6, используйте `Remove-Alias` командлет. `Remove-Item` принимается для обеспечения обратной совместимости, например для скриптов, созданных с помощью предыдущих версий PowerShell. Используйте команду, например `Remove-Item -Path Alias:aliasname` .

Чтобы создать псевдоним, доступный в каждом сеансе PowerShell, добавьте его в профиль PowerShell.
Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Псевдоним можно сохранить и повторно использовать в другом сеансе PowerShell, выполнив экспорт и импорт. Чтобы сохранить псевдоним в файл, используйте `Export-Alias` . Чтобы добавить сохраненный псевдоним в новый сеанс PowerShell, используйте `Import-Alias` .

## Связанные ссылки

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md)

[about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Remove-Alias](Remove-Alias.md)

[Remove-Item](../Microsoft.PowerShell.Management/Remove-Item.md)
