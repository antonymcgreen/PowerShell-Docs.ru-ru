---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: 48e37164f3fef84ab80ad432b996901e602c226f
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343629"
---
# Set-Acl

## Краткий обзор
Изменяет дескриптор безопасности указанного элемента, например файла или раздела реестра.

## SYNTAX

### ByPath (по умолчанию)

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### бинпутобжект

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Acl`Командлет изменяет дескриптор безопасности указанного элемента, например файла или раздела реестра, для сопоставления значений в указанном дескрипторе безопасности.

Для использования `Set-Acl` используйте параметр **path** или **InputObject** , чтобы указать элемент, дескриптор безопасности которого необходимо изменить. Затем с помощью параметра **AclObject** или **SecurityDescriptor** предоставьте дескриптор безопасности, содержащий значения, которые необходимо применить. `Set-Acl` Применяет указанный дескриптор безопасности. Он использует значение параметра **AclObject** как модель и изменяет значения в дескрипторе безопасности элемента в соответствии со значениями параметра **AclObject**.

## Примеры

### Пример 1. копирование дескриптора безопасности из одного файла в другой

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

Эти команды копируют значения из дескриптора безопасности файла Dog.txt в дескриптор безопасности файла Cat.txt. После выполнения команд дескрипторы безопасности файлов Dog.txt и Cat.txt становятся идентичны.

Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt.
Оператор присваивания ( `=` ) сохраняет дескриптор безопасности в значении переменной $DogACL.

Вторая команда использует `Set-Acl` , чтобы изменить значения в списке ACL для Cat.txt на значения в `$DogACL` .

Значение параметра **Path** представляет сбой путь к файлу Cat.txt, Значением параметра **аклобжект** является ACL модели, в данном случае acl для Dog.txt, сохраненный в `$DogACL` переменной.

### Пример 2. Использование оператора конвейера для передачи дескриптора

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

Эта команда почти аналогична команде в предыдущем примере, за исключением того, что она использует конвейерный оператор ( `|` ) для отправки дескриптора безопасности из `Get-Acl` команды в `Set-Acl` команду.

Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt. Оператор конвейера ( `|` ) передает объект, представляющий дескриптор безопасности Dog.txt для `Set-Acl` командлета.

Вторая команда использует `Set-Acl` для применения дескриптора безопасности Dog.txt к Cat.txt.
После выполнения команды списки контроля доступа к файлам Dog.txt и Cat.txt становятся идентичны.

### Пример 3. применение дескриптора безопасности к нескольким файлам

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

Эти команды применяют дескрипторы безопасности в файле File0.txt ко всем текстовым файлам в `C:\Temp` каталоге и всем его подкаталогам.

Первая команда получает дескриптор безопасности файла File0.txt в текущем каталоге и использует оператор присваивания ( `=` ), чтобы сохранить его в `$NewACL` переменной.

Первая команда в конвейере использует командлет Get-ChildItem для получения всех текстовых файлов в `C:\Temp` каталоге. Параметр **рекурсии** расширяет команду до всех подкаталогов `C:\temp` . Параметр **include** ограничивает файлы, полученные с помощью `.txt` расширения имени файла. Параметр **Force** позволяет получить скрытые файлы, которые в противном случае были бы пропущены. (Нельзя использовать `c:\temp\*.txt` , так как **рекурсивный** параметр работает с каталогами, а не с файлами.)

Оператор конвейера ( `|` ) отправляет объекты, представляющие извлеченные файлы, в `Set-Acl` командлет, который применяет дескриптор безопасности в параметре **аклобжект** ко всем файлам в конвейере.

На практике рекомендуется использовать параметр **WhatIf** со всеми `Set-Acl` командами, которые могут повлиять на несколько элементов. В этом случае вторая команда в конвейере будет иметь значение `Set-Acl -AclObject $NewAcl -WhatIf` . Она выводит на экран список файлов, к которым применяется команда. После просмотра результата можно выполнить команду еще раз без параметра **WhatIf** .

### Пример 4. Отключение наследования и сохранение унаследованных правил доступа

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

Эти команды будут отключать наследование доступа из родительских папок, сохраняя при этом существующие унаследованные правила доступа.

Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt.

Затем создаются переменные для преобразования наследуемых правил доступа в явные правила доступа. Чтобы защитить правила доступа, связанные с этим, из наследования, задайте для `$isProtected` переменной значение `$true` . чтобы разрешить наследование, задайте значение `$isProtected` `$false` . Дополнительные сведения см. в разделе [Настройка защиты правила доступа](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).
Для `$preserveInheritance` переменной задается значение `$true` , чтобы сохранить унаследованные правила доступа; значение false, чтобы удалить унаследованные правила доступа. Затем защита правила доступа обновляется с помощью метода **сетакцессрулепротектион ()** .

Последняя команда использует `Set-Acl` для применения дескриптора безопасности к Dog.txt. После выполнения команды списки управления доступом к Dog.txt, унаследованные из папки pets, будут применены непосредственно к Dog.txt, а новые политики доступа, добавленные в pets, не будут изменять доступ к Dog.txt.

### Пример 5. Предоставление администраторам полного доступа к файлу

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

Эта команда предоставит группе **Builtin \ администраторы** полный доступ к файлу Dog.txt.

Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности файла Dog.txt.

Далее создаются переменные, позволяющие предоставить группе **Builtin** \ полный доступ к файлу Dog.txt. `$identity`Для переменной задается имя [учетной записи пользователя](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor). `$fileSystemRights`Переменная, для которой задано значение фуллконтрол, может быть любым значением [филесистемригхтс](/dotnet/api/system.security.accesscontrol.filesystemrights) , указывающим тип операции, связанной с правилом доступа. `$type`Переменная со значением "Allow" указывает, следует ли разрешить или запретить операцию. `$fileSystemAccessRuleArgumentList`Переменная является списком аргументов, которая передается при создании нового объекта **филесистемакцессруле** . Затем создается новый объект **филесистемакцессруле** , и объект **филесистемакцессруле** передается в метод **сетакцессруле ()** , добавляет новое правило доступа.

Последняя команда использует `Set-Acl` для применения дескриптора безопасности к Dog.txt. По завершении выполнения команды группа **Builtin \ администраторы** будет иметь полный доступ к Dog.txt.

## PARAMETERS

### -Аклобжект

Указывает список управления доступом с необходимыми значениями свойств. `Set-Acl` изменяет список управления доступом для элемента, указанного параметром **path** или **InputObject** , в соответствии со значениями в указанном объекте безопасности.

Выходные данные команды можно сохранить `Get-Acl` в переменной, а затем использовать параметр **аклобжект** для передачи переменной или ввести `Get-Acl` команду.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Клеарцентралакцессполици

Удаляет централизованную политику доступа из указанного элемента.

Начиная с Windows Server 2012, администраторы могут использовать Active Directory и групповая политика, чтобы задать централизованные политики доступа для пользователей и групп. Дополнительные сведения см. в разделе [динамический контроль доступа: обзор сценария](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude

Исключает указанные элементы. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `*.txt` . Разрешено использовать подстановочные знаки.

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

Задает фильтр в формате или на языке поставщика. Значение этого параметра определяет параметр **Path**. Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика. Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.

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

### -Include

Изменяет только указанные элементы. Значение этого параметра определяет параметр **Path**.
Введите элемент пути или шаблон, например `*.txt` . Разрешено использовать подстановочные знаки.

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

### -InputObject

Изменяет дескриптор безопасности указанного объекта. Введите переменную, содержащую объект, либо команду, которая его возвращают.

Объект нельзя передать в конвейер, чтобы изменить его `Set-Acl` . Вместо этого настроить параметр **InputObject** прямо в команде.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Изменяет дескриптор безопасности указанного элемента. В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки ( `'` ).
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий измененный дескриптор безопасности. По умолчанию этот командлет не создает выходные данные.

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

### -Path

Изменяет дескриптор безопасности указанного элемента. Введите путь к элементу, например, путь к файлу или ключу реестра. Разрешено использовать подстановочные знаки.

Если объект безопасности передается в `Set-Acl` (с помощью параметров **Аклобжект** или **SecurityDescriptor** или путем передачи объекта безопасности из Get-Acl в `Set-Acl` ), а параметр **пути** (имя и значение) не указан, `Set-Acl` используется путь, включенный в объект безопасности.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### System. Security. AccessControl. Обжектсекурити, System. Security. AccessControl. Коммонсекуритидескриптор

Объект ACL или дескриптор безопасности можно передать в `Set-Acl` .

## Выходные данные

### System. Security. AccessControl. FileSecurity

По умолчанию не `Set-Acl` создает никаких выходных данных. но при использовании параметра **Passthru** создает объект безопасности. Тип объекта безопасности зависит от типа элемента.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

`Set-Acl`Командлет поддерживается в файловой системе PowerShell и поставщиках реестра. а значит его можно использовать для изменения дескрипторов безопасности файлов, каталогов и разделов реестра.

## Связанные ссылки

[Get-Acl](Get-Acl.md)

[филесистемакцессруле](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[Обжектсекурити. Сетакцессрулепротектион](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[филесистемригхтс](/dotnet/api/system.security.accesscontrol.filesystemrights)
