---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: e848cc8c77e1d0dff6eb1f98d56c8ed37e44a653
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692808"
---
# Get-Item

## Краткий обзор
Получает элемент в указанном расположении.

## SYNTAX

### Путь (по умолчанию)

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### LiteralPath

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Item`Командлет возвращает элемент в указанном расположении. Он не получает содержимое элемента в расположении, если только вы не используете подстановочный знак ( `*` ) для запроса всего содержимого элемента.

Этот командлет используется поставщиками PowerShell для перемещения по различным типам хранилищ данных.

## Примеры

### Пример 1. Получение текущего каталога

В этом примере возвращается текущий каталог. Точка (".") представляет элемент в текущем расположении (а не его содержимом).

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### Пример 2. получение всех элементов в текущем каталоге

Этот пример возвращает все элементы в текущем каталоге. Символ-шаблон ( `*` ) представляет все содержимое текущего элемента.

```powershell
Get-Item *
```

```output
Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006   9:29 AM            Logs
d----         7/26/2006   9:26 AM            Recs
-a---         7/26/2006   9:28 AM         80 date.csv
-a---         7/26/2006  10:01 AM         30 filenoext
-a---         7/26/2006   9:30 AM      11472 process.doc
-a---         7/14/2006  10:47 AM         30 test.txt
```

### Пример 3. Получение текущего каталога диска

В этом примере возвращается текущий каталог `C:` диска. Извлекаемый объект представляет только каталог, но не его содержимое.

```powershell
Get-Item C:\
```

### Пример 4. Получение элементов на указанном диске

В этом примере выполняется получение элементов на `C:` диске. Подстановочный знак ( `*` ) представляет все элементы в контейнере, а не только контейнер.

```powershell
Get-Item C:\*
```

В PowerShell используйте одну звездочку ( `*` ) для получения содержимого вместо традиционной `*.*` . Формат интерпретируется буквально, поэтому `*.*` не извлекаются каталоги или имена файлов без точки.

### Пример 5. получение свойства в указанном каталоге

В этом примере возвращается свойство **lastAccessTime** `C:\Windows` каталога. **LastAccessTime** — это только одно свойство каталогов файловой системы. Чтобы просмотреть все свойства каталога, введите `(Get-Item <directory-name>) | Get-Member` .

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### Пример 6. Отображение содержимого раздела реестра

В этом примере показано содержимое раздела реестра **Microsoft. PowerShell** . Этот командлет можно использовать вместе с поставщиком реестра PowerShell для получения разделов и подразделов реестра, но `Get-ItemProperty` для получения значений и данных реестра необходимо использовать командлет.

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### Пример 7. Получение элементов в каталоге с исключением

Этот пример получает элементы в каталоге Windows с именами, которые содержат точку ( `.` ), но не начинаются с `w*` . Этот пример работает только в том случае, если путь содержит подстановочный знак ( `*` ) для указания содержимого элемента.

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### Пример 8. Получение сведений о hardlink

В PowerShell 6,2 для получения сведений о hardlink было добавлено альтернативное представление. Чтобы получить сведения о hardlink, передайте выходные данные в `Format-Table -View childrenWithHardlink`

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

### Пример 9. выходные данные для экспериментальной Псуниксфилестат функции

В PowerShell 7 в системах UNIX экспериментальная функция **псуниксфилестат** предоставляет выходные данные, подобные UNIX:

```powershell
PS> Get-Item /Users
```

```Output
    Directory: /

UnixMode    User  Group   LastWriteTime      Size  Name
--------    ----  -----   -------------      ----  ----
drwxr-xr-x  root  admin   12/20/2019 11:46   192   Users
```

Новые свойства, которые теперь являются частью выходных данных:

- **Униксмоде** — это разрешения файла, представленные в системе UNIX.
- **Пользователь** является владельцем файла
- **Группа** является владельцем группы
- **Размер** — это размер файла или каталога, представленный в системе UNIX.

## PARAMETERS

### -Stream

> [!NOTE]
> Этот параметр доступен только в Windows.

Возвращает указанный альтернативный файловый поток NTFS из файла. Введите имя потока. Поддерживаются подстановочные знаки. Чтобы получить все потоки, используйте звездочку ( `*` ). Этот параметр не является допустимым для папок.

**Stream** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Item` командлет.
Этот параметр работает только на дисках с файловой системой.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No alternate file streams
Accept pipeline input: False
Accept wildcard characters: True
```

### -Credential

> [!NOTE]
> Этот параметр не поддерживается поставщиками, установленными с помощью PowerShell.
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

Задает фильтр для уточнения параметра **пути** . Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим фильтры. Фильтры более эффективны, чем другие параметры. Поставщик применяет фильтр, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения. Строка фильтра передается в API .NET для перечисления файлов. API поддерживает только `*` `?` подстановочные знаки и.

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

Указывает, что этот командлет получает элементы, доступ к которым в противном случае невозможен, например скрытые элементы.
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

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `*.txt` . Можно использовать подстановочные знаки. Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

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
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Определяет путь к элементу. Этот командлет возвращает элемент в указанном расположении. Можно использовать подстановочные знаки. Этот параметр является обязательным, но **путь к** имени параметра является необязательным.

Используйте точку ( `.` ), чтобы указать текущее расположение. Используйте подстановочный знак ( `*` ), чтобы указать все элементы в текущем расположении.

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

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь.

## Выходные данные

### System.Object

Этот командлет возвращает объекты, которые он получает. Тип определяется типом объектов в пути.

## ПРИМЕЧАНИЯ

Этот командлет не имеет **рекурсивного** параметра, так как он получает только элемент, а не его содержимое.
Для рекурсивного получения содержимого элемента используйте `Get-ChildItem` .

Для перемещения по реестру используйте этот командлет для получения разделов реестра и `Get-ItemProperty` для получения значений и данных реестра. Параметры реестра являются свойствами раздела реестра.

Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Get-PSProvider](Get-PSProvider.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
