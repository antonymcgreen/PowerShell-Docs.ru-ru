---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 859738998de9d2a61a5fb7d9f39ff6ef8b74ad4d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228221"
---
# Clear-History

## Краткий обзор
Удаляет записи из журнала команд сеанса PowerShell.

## SYNTAX

### Идпараметер (по умолчанию)

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### коммандлинепараметер

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## DESCRIPTION

`Clear-History` Удаляет журнал команд из сеанса PowerShell. Каждый сеанс PowerShell имеет собственный журнал команд. Чтобы отобразить журнал команд, используйте `Get-History` командлет.

По умолчанию `Clear-History` удаляет весь журнал команд из сеанса PowerShell. `Clear-History`Для удаления выбранных команд можно использовать параметры.

`Clear-History` не очищает `PSReadLine` файл журнала команд. `PSReadLine`Модуль хранит файл журнала, содержащий все команды PowerShell из каждого сеанса PowerShell. В командной строке PowerShell используйте клавиши со стрелками вверх и вниз для прокрутки журнала команд. Чтобы отобразить `PSReadLine` конфигурацию для журнала команд, используйте `Get-PSReadLineOption` .
`PSReadLine` поставляется с PowerShell 5,0 и более поздних версий. Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## Примеры

### Пример 1. Удаление журнала команд из сеанса PowerShell

Эта команда удаляет все команды из журнала сеанса PowerShell.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location .\Test
   2 Update-Help
   3 Set-Location C:\Test\Logs
   4 Get-Location
```

```powershell
Clear-History
Get-History
```

```Output
  Id CommandLine
  -- -----------
   5 Clear-History
```

`Get-History`Командлет отображает журнал сеанса PowerShell. `Clear-History` Удаляет весь журнал команд. `Get-History` отображает обновленный журнал команд и подтверждает, что предыдущая история была удалена.

### Пример 2. Удаление последних команд

Эта команда использует параметры **Count** и **новейшие** для удаления последних команд из журнала сеанса PowerShell.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Count 5 -Newest
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
  11 Clear-History -Count 5 -Newest
```

`Get-History`Командлет отображает журнал сеанса PowerShell. `Clear-History` используется для удаления журнала команд. Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор** . **Последний** параметр указывает, что из журнала удаляются последние команды. `Get-History`отображает обновленный журнал команд и подтверждает, что были удалены пять последних команд с **идентификатором 6**  -  **ID 10** .

### Пример 3. Удаление команд, соответствующих указанным условиям

Эта команда удаляет команды, соответствующие определенным условиям, определенным параметром **commandline** .

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
```

```powershell
Clear-History -CommandLine *Help*, *Syntax
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   4 Get-Command Clear-History -ShowCommandInfo
   8 Clear-History -CommandLine *Help*, *Syntax
```

`Get-History`Командлет отображает журнал сеанса PowerShell. `Clear-History` Удаляет журнал команд. Параметр **commandline** указывает команды, которые содержат **справку** или End с **синтаксисом** . `Get-History` отображает обновленный журнал команд и подтверждает удаление команд с **идентификатором 3** , **идентификатор 5** , **идентификатор 6** и **идентификатор 7** .

### Пример 4. Удаление команд по идентификационному номеру

Эта команда удаляет определенные элементы журнала с помощью **идентификатора** . Чтобы удалить несколько команд, отправьте список **идентификаторов** с разделителями-запятыми.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   3 Get-Help Get-Alias
   4 Get-Command Clear-History
   5 Get-Command Clear-History -Syntax
   6 Get-Command Clear-History -ShowCommandInfo
```

```powershell
Clear-History -Id 3, 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   4 Get-Command Clear-History
   6 Get-Command Clear-History -ShowCommandInfo
   7 Get-History
   8 Clear-History -Id 3, 5
```

`Get-History`Командлет отображает журнал сеанса PowerShell. `Clear-History` Удаляет журнал команд. Параметр **ID** указывает, какие команды следует удалить. `Get-History` Отображение обновленного журнала команд и подтверждение удаления **идентификатора 3** и **идентификатора 5** .

### Пример 5. Удаление команд по идентификатору и количеству

Эта команда использует параметры **ID** и **Count** для удаления журнала команд. Команды удаляются из указанного **идентификатора** в обратном порядке, от новых к старым.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Id 7 -Count 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
  11 Clear-History -Id 7 -Count 5
```

`Get-History`Командлет отображает журнал сеанса PowerShell. `Clear-History` Удаляет журнал команд. Параметр **ID** указывает, что начинается с **ID 7** . Параметр **Count** указывает удалить пять команд, включая заданный **идентификатор** . `Get-History`отображает обновленный журнал команд и подтверждает удаление пяти команд, **идентификатор 3**  -  **ID 7** .

## PARAMETERS

### -CommandLine

Удаляет журнал команд из сеанса PowerShell. Строка должна быть точным совпадением или использовать подстановочные знаки для сопоставления команд в журнале сеанса PowerShell, который отображается в `Get-History` . Если ввести более одной строки, `Clear-History` удаляет команды, соответствующие любой из строк. Параметр **commandline** можно использовать с **Count** .

Для строк с пробелом используйте одинарные кавычки. Дополнительные сведения см. в разделе [about_Quoting_Rules](About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: CommandLineParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### — Количество

Указывает количество записей журнала, которые `Clear-History` удаляются. Команды удаляются по порядку, начиная с самой старой записи в журнале.

Параметры **Count** и **ID** можно использовать совместно. Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор** . Начиная с указанного **идентификатора** , команды удаляются в обратную последовательность. Например, если **идентификатор** равен 30, а значение **счетчика** — 10, то `Clear-History` элементы удаляются с 21 до 30.

Параметры **Count** и **commandline** можно использовать совместно. **Count** указывает количество команд для удаления, соответствующих значению параметра **командной строки** . Команды удаляются в последовательном порядке.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает **идентификатор** журнала команд, который `Clear-History` удаляется. Чтобы отобразить **идентификационные** номера, используйте `Get-History` командлет. Номера **идентификаторов** являются последовательными, а команды сохраняют свой **идентификационный** номер во время сеанса PowerShell. Параметр **ID** можно использовать с параметрами **Count** и **новейшие** .

```yaml
Type: System.Int32[]
Parameter Sets: IDParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Самый новый

При использовании **последнего** параметра `Clear-History` удаляет последние записи в журнале. По умолчанию `Clear-History` удаляет самые старые записи в журнале.

**Последний** параметр можно использовать с **идентификатором** и **счетчиком** . Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор** . Начиная с указанного **идентификатора** , команды удаляются в последовательном порядке. Например, если **идентификатор** равен 30, а значение **счетчика** — 10, то `Clear-History` удаляются элементы с 30 по 39.

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

### -Confirm

Запрашивает подтверждение перед запуском `Clear-History` командлета.

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

Показывает, что произойдет при `Clear-History` запуске командлета. Командлет не выполняется.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

Вы не можете передать объекты в `Clear-History` .

## Выходные данные

### Нет

`Clear-History` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Журнал сеанса PowerShell представляет собой список команд, вводимых во время сеанса PowerShell. Вы можете просматривать журнал, добавлять и удалять команды, а также выполнять команды, хранящиеся в журнале. Дополнительные сведения см. в разделе [about_History](About/about_History.md).

Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .
Оба журнала доступны в сеансах, где загружен **PSReadLine** . Этот командлет работает только с журналом сеанса. Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## Связанные ссылки

[about_History](About/about_History.md)

[about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)

[about_Quoting_Rules](About/about_Quoting_Rules.md)

[Add-History](Add-History.md)

[Get-History](Get-History.md)

[Invoke-History](Invoke-History.md)

[Get-PSReadLineOption](/powershell/module/psreadline/get-psreadlineoption)

[Set-PSReadLineOption](/powershell/module/psreadline/set-psreadlineoption)
