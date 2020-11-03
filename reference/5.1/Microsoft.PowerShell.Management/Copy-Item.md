---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: 4c15ea0fd9c3fb3837ec2a23e8278016858df09d
ms.sourcegitcommit: 33ac34789e86ffb4e7e69453ae38fc0bd24933dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "93230542"
---
# Copy-Item

## Краткий обзор
Копирует элемент из одного расположения в другое.

## SYNTAX

### Путь (по умолчанию)

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [-FromSession <PSSession>] [-ToSession <PSSession>]
 [<CommonParameters>]
```

### LiteralPath

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [-FromSession <PSSession>] [-ToSession <PSSession>]
 [<CommonParameters>]
```

## DESCRIPTION

`Copy-Item`Командлет копирует элемент из одного расположения в другое расположение в том же пространстве имен.
Например, он может скопировать файл в папку, но не может скопировать файл на диск сертификата.

Этот командлет не вырезает и не удаляет копируемые элементы. Отдельные элементы, которые может копировать командлет, зависят от поставщика PowerShell, предоставляющего элемент. Например, он может копировать файлы и каталоги в диск файловой системы, разделы реестра и записи на диске реестра.

Этот командлет может копировать и переименовывать элементы в одной команде. Чтобы переименовать элемент, введите новое имя в качестве значения параметра **Destination** . Чтобы переименовать элемент и не копировать его, используйте `Rename-Item` командлет.

## Примеры

### Пример 1. копирование файла в указанный каталог

В этом примере файл копируется `mar1604.log.txt` в `C:\Presentation` каталог. Исходный файл не удаляется.

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### Пример 2. копирование содержимого каталога в существующий каталог

В этом примере содержимое каталога копируется `C:\Logfiles` в существующий `C:\Drawings` каталог. `Logfiles`Каталог не копируется.

Если `Logfiles` Каталог содержит файлы в подкаталогах, то эти подкаталоги копируются без изменений в их деревьях файлов. По умолчанию параметр **контейнера** имеет значение **true** , сохраняющее структуру каталогов.

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> Если необходимо включить `Logfiles` каталог в копию, удалите `\*` из **пути** .
> Пример:
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### Пример 3. копирование каталога и содержимого в новый каталог

В этом примере копируется содержимое `C:\Logfiles` исходного каталога и создается новый каталог назначения. Новый каталог назначения `\Logs` создается в `C:\Drawings` .

Чтобы включить имя исходного каталога, скопируйте его в существующий каталог назначения, как показано в **примере 2** . Или назовите новый каталог назначения так же, как и исходный каталог.

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> Если **путь** включает `\*` , все содержимое файла каталога, включая деревья подкаталогов, копируется в новый каталог назначения. Пример:
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### Пример 4. копирование файла в указанный каталог и переименование файла

В этом примере `Copy-Item` командлет используется для копирования `Get-Widget.ps1` скрипта из `\\Server01\Share` каталога в `\\Server12\ScriptArchive` каталог. В ходе операции копирования команда изменяет имя элемента с `Get-Widget.ps1` на `Get-Widget.ps1.txt` , поэтому оно может быть присоединено к сообщениям электронной почты.

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### Пример 5. копирование файла на удаленный компьютер

Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .

`Copy-Item`Командлет копирует `test.log` из `D:\Folder001` папки в `C:\Folder001_Copy` папку на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной. Исходный файл не удаляется.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### Пример 6. Копирование папки на удаленный компьютер

Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .

`Copy-Item`Командлет копирует папку в `D:\Folder002` `C:\Folder002_Copy` каталог на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной. Все вложенные папки или файлы не копируются без использования **рекурсивного** переключателя.
Операция создает папку, `Folder002_Copy` если она еще не существует.

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### Пример 7. рекурсивное копирование всего содержимого папки на удаленный компьютер

Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .

`Copy-Item`Командлет копирует все содержимое из `D:\Folder003` папки в `C:\Folder003_Copy` каталог на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной. Вложенные папки копируются без изменений в их деревьях файлов. Операция создает папку, `Folder003_Copy` если она еще не существует.

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### Пример 8. копирование файла на удаленный компьютер и его переименование

Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .

`Copy-Item`Командлет копирует `scriptingexample.ps1` из `D:\Folder004` папки в `C:\Folder004_Copy` папку на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной. В ходе операции копирования команда изменяет имя элемента с `scriptingexample.ps1` на `scriptingexample_copy.ps1` , поэтому оно может быть присоединено к сообщениям электронной почты. Исходный файл не удаляется.

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### Пример 9. Копирование удаленного файла на локальный компьютер

Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .

`Copy-Item`Командлет копирует `test.log` из удаленной `C:\MyRemoteData\` папки в локальную `D:\MyLocalData` папку, используя сведения о сеансе, хранящиеся в `$Session` переменной. Исходный файл не удаляется.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### Пример 10. копирование всего содержимого удаленной папки на локальный компьютер

Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .

`Copy-Item`Командлет копирует все содержимое из удаленной `C:\MyRemoteData\scripts` папки в локальную `D:\MyLocalData` папку, используя сведения о сеансе, хранящиеся в `$Session` переменной. Если папка Scripts содержит файлы во вложенных папках, эти вложенные папки копируются без изменений.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### Пример 11. рекурсивное копирование всего содержимого удаленной папки на локальный компьютер

Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .

`Copy-Item`Командлет копирует все содержимое из удаленной `C:\MyRemoteData\scripts` папки в локальную `D:\MyLocalData\scripts` папку, используя сведения о сеансе, хранящиеся в `$Session` переменной. Так как используется параметр **рекурсии** , операция создает папку Scripts, если она еще не существует. Если папка Scripts содержит файлы во вложенных папках, эти вложенные папки копируются без изменений.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### Пример 12. рекурсивное копирование файлов из дерева папок в текущую папку

В этом примере показано, как скопировать файлы из многоуровневой структуры папок в одну неструктурированную папку.
Первые три команды отображают существующую структуру папок и содержимое двух файлов, оба имени `file3.txt` .

```powershell
PS C:\temp\test> (Get-ChildItem C:\temp\tree -Recurse).FullName
C:\temp\tree\subfolder
C:\temp\tree\file1.txt
C:\temp\tree\file2.txt
C:\temp\tree\file3.txt
C:\temp\tree\subfolder\file3.txt
C:\temp\tree\subfolder\file4.txt
C:\temp\tree\subfolder\file5.txt

PS C:\temp\test> Get-Content C:\temp\tree\file3.txt
This is file3.txt in the root folder

PS C:\temp\test> Get-Content C:\temp\tree\subfolder\file3.txt
This is file3.txt in the subfolder

PS C:\temp\test> Copy-Item -Path C:\temp\tree -Filter *.txt -Recurse -Container:$false
PS C:\temp\test> (Get-ChildItem . -Recurse).FullName
C:\temp\test\subfolder
C:\temp\test\file1.txt
C:\temp\test\file2.txt
C:\temp\test\file3.txt
C:\temp\test\file4.txt
C:\temp\test\file5.txt

PS C:\temp\test> Get-Content .\file3.txt
This is file3.txt in the subfolder
```

`Copy-Item`Для командлета параметр **контейнера** имеет значение `$false` . В результате содержимое исходной папки копируется, но структура папок не сохраняется. Обратите внимание, что файлы с одинаковыми именами перезаписываются в папку назначения.

## PARAMETERS

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

### -Container

Указывает, что этот командлет сохраняет объекты контейнера во время операции копирования. По умолчанию параметр **контейнера** имеет значение **true** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Destination

Указывает путь к новому расположению. Значением по умолчанию является текущий каталог.

Чтобы переименовать копируемый элемент, укажите новое имя в значении параметра **Destination** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude

Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `*.txt` . Можно использовать подстановочные знаки. Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

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

Задает фильтр для уточнения параметра **пути** . Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров. Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.

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

Указывает, что этот командлет копирует элементы, которые не могут быть изменены другим способом, например копирование файла или псевдонима, доступного только для чтения.

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

### -FromSession

Указывает объект **PSSession** , из которого копируется удаленный файл. При использовании этого параметра параметры **path** и **LiteralPath** ссылаются на локальный путь на удаленном компьютере.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `"*.txt"` . Можно использовать подстановочные знаки. Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

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

Указывает путь к одному или нескольким расположениям. Значение **LiteralPath** используется точно так же, как типизировано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым выполняется работа. По умолчанию этот командлет не создает никаких выходных данных.

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

Указывает в виде массива строк путь к копируемым элементам. Можно использовать подстановочные знаки.

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

Указывает, что этот командлет выполняет рекурсивную копию.

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

### -ToSession

Указывает объект **PSSession** , в который копируется удаленный файл. При использовании этого параметра параметр **назначения** ссылается на локальный путь на удаленном компьютере.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction

Включает команду в активную транзакцию. Этот параметр доступен только при выполнении транзакции. Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

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

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь.

## Выходные данные

### Нет или объект, представляющий скопированный элемент

При использовании параметра **PassThru** этот командлет возвращает объект, представляющий скопированный элемент. В противном случае этот командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Clear-Item](Clear-Item.md)

[Get-Item](Get-Item.md)

[Get-PSProvider](Get-PSProvider.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)
