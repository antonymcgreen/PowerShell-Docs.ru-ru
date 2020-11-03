---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: f73f22ff81a5aea6bff272328f0c523cd93a9c0d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228825"
---
# Get-PSProvider

## Краткий обзор
Возвращает сведения об указанном поставщике PowerShell.

## SYNTAX

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-PSProvider`Командлет получает поставщиков PowerShell в текущем сеансе.
Можно получить определенный диск или все диски в сеансе.

Поставщики PowerShell позволяют обращаться к различным хранилищам данных, как будто они являются дисками файловой системы.
Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Примеры

### Пример 1. Отображение списка всех доступных поставщиков

```powershell
Get-PSProvider
```

Эта команда отображает список всех доступных поставщиков PowerShell.

### Пример 2. Отображение списка всех поставщиков PowerShell, начинающихся с указанных букв

```powershell
Get-PSProvider f*, r* | Format-List
```

Эта команда отображает список всех поставщиков PowerShell с именами, начинающимися с буквы f или r.

### Пример 3. Поиск оснасток или модулей, которые добавляют поставщики в сеанс

```powershell
Get-PSProvider | Format-Table name, module, pssnapin -auto
```

```Output
Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security
```

```powershell
Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}
```

```Output
Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

Эти команды находят оснастки или модули PowerShell, которые добавляют поставщиков в ваш сеанс.
Все элементы PowerShell, включая поставщики, создаются в оснастке или модуле.

Эти команды используют свойства PSSnapin и Module объекта **провидеринфо** , который `Get-PSProvider` возвращает.
Значения этих свойств указывают на имя оснастки или модуля, который добавил поставщика.

Первая команда возвращает сведения о всех поставщиках в рамках сеанса и форматирует их в виде таблицы, содержащей значения свойств Name, Module и PSSnapin.

Вторая команда использует `Where-Object` командлет для получения поставщиков, поступающих от оснастки **Microsoft. PowerShell. Security** .

### Пример 4. разрешение пути к свойству Home поставщика файловой системы

```powershell
C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

```powershell
PS C:\> (get-psprovider FileSystem).home
```

```Output
C:\Users\User01
```

В этом примере показано, что символ тильды (~) представляет значение свойства **Home** поставщика FileSystem.
Значение свойства **Home** является необязательным, но для поставщика **FileSystem** оно определяется как `$env:homedrive\$env:homepath` или `$home` .

## PARAMETERS

### -PSProvider

Указывает имя или имена поставщиков PowerShell, о которых этот командлет получает сведения.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### String[]

В этот командлет можно передать одну или несколько строк имени поставщика.

## Выходные данные

### System. Management. Automation. Провидеринфо

Этот командлет возвращает объекты, которые представляют поставщиков PowerShell в сеансе.

## ПРИМЕЧАНИЯ

## Связанные ссылки
