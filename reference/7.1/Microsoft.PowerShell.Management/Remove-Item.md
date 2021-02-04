---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: c4a0243c528cbe1a28cad99cf6fa8d91018d9b3c
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692689"
---
# Remove-Item

## Краткий обзор
Удаляет указанные элементы.

## SYNTAX

### Путь (по умолчанию)

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### LiteralPath

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

`Remove-Item`Командлет удаляет один или несколько элементов. Так как он поддерживается многими поставщиками, он может удалять множество различных типов элементов, включая файлы, папки, разделы реестра, переменные, псевдонимы и функции.

## Примеры

### Пример 1. Удаление файлов, имеющих любое расширение имени файла

В этом примере из папки удаляются все файлы, имена которых содержат точку ( `.` ) `C:\Test` . Поскольку команда задает точку, команда не удаляет папки или файлы, не имеющие расширения имени файла.

```powershell
Remove-Item C:\Test\*.*
```

### Пример 2. Удаление некоторых файлов документов в папке

В этом примере удаляется из текущей папки все файлы, имеющие `.doc` расширение имени файла, и имя, которое не включает `*1*` .

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

`*`Для указания содержимого текущей папки используется подстановочный знак (). Для указания удаляемых файлов используются параметры **include** и **Exclude** .

### Пример 3. Удаление скрытых файлов, доступ только для чтения

Эта команда удаляет файл, который как *скрытый* , так и *только для чтения*.

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

Для указания файла используется параметр **path** . Для его удаления используется параметр **Force** . Без **принудительного** использования нельзя удалять файлы, которые _доступны только для чтения_ или _скрыты_ .

### Пример 4. рекурсивное удаление файлов во вложенных папках

Эта команда рекурсивно удаляет все CSV-файлы в текущей папке и во всех вложенных папках.

Поскольку **рекурсивный** параметр в `Remove-Item` имеет известную ошибку, команда в этом примере использует `Get-ChildItem` для получения нужных файлов, а затем использует оператор конвейера для передачи их в `Remove-Item` .

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

В `Get-ChildItem` команде **path** имеет значение ( `*` ), которое представляет содержимое текущей папки. Он использует параметр **include** для указания типа CSV-файла и использует рекурсию, чтобы сделать **возможной** рекурсивный выбор. При попытке указать тип файла путь, например `-Path *.csv` , командлет интерпретирует тему поиска как файл, не имеющий дочерних элементов, и **рекурсия** завершается сбоем.

### Пример 5. рекурсивное удаление подразделов

Эта команда удаляет раздел реестра "Олдапп" и все его подразделы и значения. Он использует `Remove-Item` для удаления ключа. Путь указан, но необязательное имя параметра (**путь**) пропущено.

**Рекурсивный параметр удаляет** все содержимое ключа "олдапп" рекурсивно. Если ключ содержит подразделы и не указан параметр **рекурсии** , вам будет предложено подтвердить удаление содержимого ключа.

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### Пример 6. Удаление файлов со специальными символами

В следующем примере показано, как удалить файлы, содержащие специальные символы, такие как квадратные скобки или круглые скобки.

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### Пример 7. Удаление альтернативного потока данных

В этом примере показано, как использовать динамический параметр **Stream** `Remove-Item` командлета для удаления альтернативного потока данных. Параметр Stream появился в Windows PowerShell 3,0.

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

Параметр **Stream** `Get-Item` получает `Zone.Identifier` поток `Copy-Script.ps1` файла. `Remove-Item` использует параметр **Stream** для удаления `Zone.Identifier` потока файла. Наконец, `Get-Item` командлет показывает, что `Zone.Identifier` поток удален.

## PARAMETERS

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.
> Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude

Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `*.txt` . Можно использовать подстановочные знаки. Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Задает фильтр для уточнения параметра **пути** . Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров. Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md). Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Заставляет командлет удалять элементы, которые в противном случае не могут быть изменены, например скрытые или только для чтения, а также псевдонимы или переменные только для чтения. С помощью этого командлета нельзя удалять постоянные псевдонимы или переменные.
Применение этого параметра зависит от конкретного поставщика. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md). Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.

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

### -Include

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `"*.txt"` . Можно использовать подстановочные знаки. Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LiteralPath

Указывает путь к одному или нескольким расположениям. Значение **LiteralPath** используется точно так же, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь удаляемых элементов.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Recurse

Указывает, что этот командлет удаляет элементы в указанных расположениях и во всех дочерних элементах расположений.

При использовании с параметром **include** **рекурсивный** параметр может не удалить все вложенные папки или все дочерние элементы. Это известная проблема. В качестве обходного решения попробуйте выполнить конвейерную `Get-ChildItem -Recurse` команду `Remove-Item` , как описано в примере 4 в этом разделе.

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

### -Stream

> [!NOTE]
> Этот параметр доступен только в Windows.

Параметр **потока** — это динамический параметр, к которому добавляется поставщик FileSystem `Remove-Item` .
Этот параметр работает только на дисках с файловой системой.

Можно использовать `Remove-Item` для удаления альтернативного потока данных, например `Zone.Identifier` .
Однако не рекомендуется отменять проверки безопасности, которые блокируют файлы, загруженные из Интернета. Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Confirm

Запрос подтверждения перед выполнением командлета. Дополнительные сведения см. в следующих статьях:

- [about_Preference_Variables](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [about_Functions_CmdletBindingAttribute](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

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

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.

## Выходные данные

### Нет

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

`Remove-Item`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

При попытке удалить папку, содержащую элементы, не используя параметр **рекурсии** , командлет запрашивает подтверждение. Использование не `-Confirm:$false` подавляет запрос. Это сделано намеренно.

## Связанные ссылки

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Preference_Variables](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[about_Functions_CmdletBindingAttribute](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)
