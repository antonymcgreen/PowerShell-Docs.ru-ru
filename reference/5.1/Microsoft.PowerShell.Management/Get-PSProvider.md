---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228365"
---
# Get-PSProvider

## Краткий обзор
Получает сведения об указанном поставщике Windows PowerShell.

## SYNTAX

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-psprovider** получает поставщиков Windows PowerShell в текущем сеансе.
Можно получить определенный диск или все диски в сеансе.

Поставщики Windows PowerShell позволяют обращаться к различным хранилищам данных так же, как к дискам файловой системы.
Сведения о поставщиках Windows PowerShell см. в разделе "about_Providers".

## Примеры

### Пример 1. Отображение списка всех доступных поставщиков

```
PS C:\> Get-PSProvider
```

Эта команда выводит список доступных поставщиков Windows PowerShell.

### Пример 2. Отображение списка всех поставщиков Windows PowerShell, начинающихся с указанных букв

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

Эта команда отображает список всех поставщиков Windows PowerShell с именами, начинающимися с буквы f или r.

### Пример 3. Поиск оснасток или модулей, которые добавляют поставщики в сеанс

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

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

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

Эти команды обнаруживают оснастки или модули Windows PowerShell, которые добавили поставщиков в текущий сеанс.
Источником всех элементов Windows PowerShell, включая поставщиков, являются оснастки или модули.

Эти команды используют свойства PSSnapin и Module объекта **провидеринфо** , возвращаемого командлетом **Get-psprovider** .
Значения этих свойств указывают на имя оснастки или модуля, который добавил поставщика.

Первая команда возвращает сведения о всех поставщиках в рамках сеанса и форматирует их в виде таблицы, содержащей значения свойств Name, Module и PSSnapin.

Вторая команда использует командлет Where-Object для получения поставщиков, которые поступают из оснастки **Microsoft. PowerShell. Security** .

### Пример 4. разрешение пути к свойству Home поставщика файловой системы

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

В этом примере показано, что символ тильды (~) представляет значение свойства Home поставщика FileSystem.
Значение свойства Home является необязательным, но для поставщика FileSystem оно определяется как $env: хомедриве \$ env: хомепас или $Home.

## PARAMETERS

### -PSProvider
Указывает имя или имена поставщиков Windows PowerShell, о которых этот командлет получает сведения.

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
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### String[]

В этот командлет можно передать одну или несколько строк имени поставщика.

## Выходные данные

### System. Management. Automation. Провидеринфо
Этот командлет возвращает объекты, которые представляют поставщиков Windows PowerShell в сеансе.

## ПРИМЕЧАНИЯ

## Связанные ссылки

## Связанные ссылки
