---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 79d6337574c2e354e49926fa894415fca2469ba7
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "93230446"
---
# Get-Location

## Краткий обзор
Возвращает сведения о текущем рабочем расположении или стеке расположения.

## SYNTAX

### Расположение (по умолчанию)

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [<CommonParameters>]
```

### Стек

```
Get-Location [-Stack] [-StackName <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Location`Командлет возвращает объект, представляющий текущий каталог, во многом похоже на команду Print Work Directory (PWD).

При переходе между дисками PowerShell в PowerShell остается расположение на каждом диске. С помощью этого командлета можно найти расположение на каждом диске.

С помощью этого командлета можно получить текущий каталог во время выполнения и использовать его в функциях и скриптах, например в функции, которая отображает текущий каталог в командной строке PowerShell.

Этот командлет также можно использовать для вывода расположений в стеке расположений. Дополнительные сведения см. в примечаниях и описаниях параметров **Stack** и **StackName** .

## Примеры

### Пример 1. Отображение текущего расположения диска

Эта команда отображает ваше расположение на текущем диске PowerShell.

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

Например, если вы используете `Windows` каталог `C:` диска, он отображает путь к этому каталогу.

### Пример 2. Отображение текущего расположения для разных дисков

В этом примере показано использование `Get-Location` для вывода текущего расположения на разных дисках PowerShell. `Set-Location` используется для изменения расположения на несколько разных путей в разных Псдривес.

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### Пример 3. получение расположений с помощью стеков

В этом примере показано, как использовать параметры **Stack** и **StackName** `Get-Location` для перечисления расположений в текущем стеке расположения и альтернативных стеках расположения.

`Push-Location`Командлет используется для изменения трех различных расположений. Третья отправка использует другое имя стека. Параметр **Stack** объекта `Get-Location` отображает содержимое стека по умолчанию. Параметр **StackName** объекта `Get-Location` отображает содержимое стека с именем `Stack2` .

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### Пример 4. Настройка командной строки PowerShell

В этом примере показано, как настроить командную строку PowerShell.

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

Функция, определяющая запрос `Get-Location` , включает команду, которая выполняется при появлении запроса в консоли.

Формат командной строки PowerShell по умолчанию определяется специальной функцией с именем `prompt` . Вы можете изменить запрос в консоли, создав новую функцию с именем `prompt` .

Чтобы просмотреть текущую функцию Prompt, введите следующую команду: `Get-Content Function:\prompt`

## PARAMETERS

### -PSDrive

Возвращает текущее расположение в указанном диске PowerShell.

Например, если вы используете `Cert:` диск, этот параметр можно использовать для поиска текущего расположения на `C:` диске.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSProvider

Возвращает текущее расположение на диске, поддерживаемое указанным поставщиком PowerShell.
Если указанный поставщик поддерживает более одного диска, этот командлет возвращает расположение на последнем доступном диске.

Например, если вы используете `C:` диск, этот параметр можно использовать для поиска текущего расположения на дисках поставщика **реестра** PowerShell.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Stack

Указывает, что этот командлет отображает расположения, добавленные в текущий стек расположений. Вы можете добавлять расположения в стеки с помощью `Push-Location` командлета.

Чтобы отобразить расположения в другом стеке расположения, используйте параметр **StackName** . Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StackName

Указывает в виде массива строк именованные стеки расположения. Введите одно или несколько имен стеков расположения.

Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** . Чтобы сделать стек расположения текущим стеком расположения, используйте `Set-Location` командлет.

Этот командлет не может отобразить расположения в неименованном стеке по умолчанию, если только это не текущий стек.

```yaml
Type: System.String[]
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

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. PathInfo или System. Management. Automation. Пасинфостакк

При использовании параметров **Stack** или **StackName** этот командлет возвращает объект **пасинфостакк** . В противном случае возвращается объект **PathInfo** .

## ПРИМЕЧАНИЯ

PowerShell поддерживает несколько пространств выполнения для каждого процесса. Каждое пространство выполнения имеет свой собственный _текущий каталог_ .
Это не то же самое, что `[System.Environment]::CurrentDirectory` . Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.
`Get-Location`Командлет возвращает текущий каталог текущего пространства выполнения PowerShell.

Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы получить список поставщиков в сеансе, введите `Get-PSProvider` . Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Способы, с помощью которых взаимодействуют параметры **psprovider** , **PSDrive** , **Stack** и **StackName** , зависят от поставщика. Некоторые сочетания приводят к ошибкам, например указание и диска, и поставщика, который не предоставляет доступ к этому диску. Если параметры не указаны, этот командлет возвращает объект **PathInfo** для поставщика, который содержит текущее рабочее расположение.

Стек — это последний список, в котором доступен только последний добавленный элемент. Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке. PowerShell позволяет хранить расположения поставщиков в стеках расположений. PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения. Если имя стека не указано, PowerShell использует текущий стек расположения. По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.

Для управления стеками расположений используйте `*-Location` командлеты PowerShell, как показано ниже.

- Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.

- Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.

- Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета. Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.

- Чтобы создать новый стек расположений, используйте параметр **StackName** `Push-Location` командлета.
  Если указан несуществующий стек, `Push-Location` создает стек.

- Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.

Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.
Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать этот командлет для вывода расположений в неименованном стеке. Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$null` или пустой строкой ( `""` ).

## Связанные ссылки

[Pop-Location](Pop-Location.md)

[Push-Location](Push-Location.md)

[Set-Location](Set-Location.md)

