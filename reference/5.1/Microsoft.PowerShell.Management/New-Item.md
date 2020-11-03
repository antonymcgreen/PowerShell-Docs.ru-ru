---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227973"
---
# New-Item

## Краткий обзор
Создает новый элемент.

## SYNTAX

### Path (по умолчанию)

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### имя

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

`New-Item`Командлет создает новый элемент и задает его значение. Типы элементов, которые могут быть созданы, зависят от расположения элемента. Например, в файловой системе `New-Item` создаются файлы и папки. В реестре `New-Item` создает разделы и записи реестра.

`New-Item` также может задавать значения создаваемых элементов. Например, при создании нового файла `New-Item` может добавить в файл начальное содержимое.

## Примеры

### Пример 1. Создание файла в текущем каталоге

Эта команда создает текстовый файл с именем "testfile1.txt" в текущем каталоге. Точка (".") в значении параметра **path** указывает текущий каталог. Текст в кавычках, следующий за параметром **value** , добавляется в файл как содержимое.

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### Пример 2. Создание каталога

Эта команда создает каталог с именем "файл_журнала" на `C:` диске. Параметр **ItemType** указывает, что новый элемент является каталогом, а не файлом или другим объектом файловой системы.

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### Пример 3. Создание профиля

Эта команда создает профиль PowerShell по пути, указанному `$profile` переменной.

Для настройки PowerShell можно использовать профили. `$profile` — Это автоматическая (встроенная) переменная, в которой хранится путь и имя файла профиля "CurrentUser/CurrentHost". По умолчанию профиль не существует, несмотря на то, что PowerShell сохраняет путь и имя файла для него.

В этой команде `$profile` переменная представляет путь к файлу. Параметр **ItemType** указывает, что команда создает файл. Параметр **Force** позволяет создать файл в пути профиля, даже если каталоги в пути не существуют.

После создания профиля можно ввести в профиль псевдонимы, функции и скрипты, чтобы настроить оболочку.

Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) и [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> При создании файла с помощью этого метода полученный файл кодируется как UTF-8 без отметки порядка байтов (BOM).

### Пример 4. Создание каталога в другом каталоге

В этом примере создается новый каталог Scripts в каталоге "К:\пс-тест".

Имя нового элемента каталога, «Scripts», включается в значение параметра **path** , а не указывается в значении **Name** . Как указывается в синтаксисе, любая форма команды допустима.

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### Пример 5. Создание нескольких файлов

В этом примере создаются файлы в двух разных каталогах. Поскольку **путь** принимает несколько строк, его можно использовать для создания нескольких элементов.

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### Пример 6. Использование параметра-Force для попыток повторного создания папок

В этом примере создается папка с файлом внутри. Затем пытается создать ту же папку с помощью `-Force` . Она не перезаписывает папку, а просто возвращает существующий объект Folder с нетронутым файлом.

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### Пример 7. Использование параметра-Force для перезаписи существующих файлов

В этом примере создается файл со значением, а затем создается файл повторно с помощью `-Force` . При этом существующий файл перезаписывается, и его содержимое будет потеряно, как видно в свойстве Length.

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> При использовании `New-Item` с `-Force` параметром для создания разделов реестра команда будет вести себя так же, как при перезаписи файла. Если раздел реестра уже существует, ключ и все его свойства и значения будут перезаписаны пустым ключом реестра.

## PARAMETERS

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell. Чтобы олицетворить другого пользователя или повысить свои учетные данные при запуске этого командлета, используйте `Invoke-Command` .

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

### -Force

Заставляет этот командлет создать элемент, записывающий существующий элемент только для чтения. Применение этого параметра зависит от конкретного поставщика. Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.

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

### -ItemType

Указывает тип нового элемента, заданный поставщиком. Доступные значения этого параметра зависят от текущего используемого поставщика.

Если расположение находится в `FileSystem` диске, допустимы следующие значения:

- Файл
- Каталог
- SymbolicLink
- Соединение
- HardLink

При создании файла с помощью этого метода полученный файл кодируется как UTF-8 без отметки порядка байтов (BOM).

На `Certificate` диске можно указать следующие значения:

- Поставщик Certificate
- Сертификат
- Магазин
- StoreLocation

Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает имя нового элемента. Можно указать имя нового элемента в значении параметра **Name** или **path** , а также указать путь к новому элементу в значении **имени** или **пути** . Имена элементов, переданных с помощью параметра **Name** , создаются относительно значения параметра **path** .

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь к расположению нового элемента. По умолчанию используется текущее расположение, когда **путь** опущен. Можно указать имя нового элемента в **поле имя** или включить его в **путь** . Имена элементов, переданных с помощью параметра **Name** , создаются относительно значения параметра **path** .

Для этого командлета параметр **path** работает как параметр **LiteralPath** других командлетов.
Символы-шаблоны не обрабатываются. Все символы передаются поставщику расположения. Поставщик может не поддерживать все символы. Например, нельзя создать имя файла, содержащее символ звездочки ( `*` ).

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
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

### -Value

Указывает значение нового элемента. Можно также передать значение в `New-Item` .

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Object

В этот командлет можно передать значение для нового элемента.

## Выходные данные

### System.Object

Этот командлет возвращает элемент, который он создает.

## ПРИМЕЧАНИЯ

`New-Item` предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
