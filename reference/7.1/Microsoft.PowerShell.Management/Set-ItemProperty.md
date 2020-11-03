---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: 26f26ff48d0c2d68c9c814da192ce1846edfe9b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226438"
---
# Set-ItemProperty

## Краткий обзор
Создает или изменяет значение свойства элемента.

## SYNTAX

### Пропертивалуепассет (по умолчанию)

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### пропертипсобжектпассет

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### пропертивалуелитералпассет

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### пропертипсобжектлитералпассет

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## DESCRIPTION

`Set-ItemProperty`Командлет изменяет значение свойства указанного элемента.
Его можно использовать для установки и изменения свойств элементов.
Например, можно использовать `Set-ItemProperty` для установки значения свойства **IsReadOnly** объекта файла в значение `$True` .

Также используется `Set-ItemProperty` для создания и изменения значений и данных реестра.
Например, с его помощью можно добавить в раздел реестра новую запись и установить или изменить ее значение.

## Примеры

### Пример 1. Задание свойства файла

Эта команда задает для свойства **IsReadOnly** файла "final.doc" значение "true".
Он использует **путь** для указания файла, **имя** для указания имени свойства, а параметр **value** — для указания нового значения.

Файл является объектом **System. IO. FileInfo** , а свойство **IsReadOnly** — только одним из его свойств.
Чтобы просмотреть все свойства, введите `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` .

`$true`Автоматическая переменная представляет значение "true".
Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### Пример 2. Создание записи и значения реестра

В этом примере показано, как использовать `Set-ItemProperty` для создания новой записи реестра и для назначения значения записи. Он создает запись "NoOfEmployees" в ключе "Контосокомпани" в `HKLM\Software` разделе Key и присваивает ей значение 823.

Поскольку записи реестра считаются свойствами разделов реестра, которые являются элементами, используются `Set-ItemProperty` для создания записей реестра, а также для установки и изменения их значений.

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

Первая команда создает запись реестра.
В нем используется **путь** для указания пути к `HKLM:` диску и ключа "софтваре\микомпани".
Команда использует **имя** , чтобы указать имя и **значение** записи для указания значения.

Вторая команда использует `Get-ItemProperty` командлет для просмотра новой записи реестра.
Если используются `Get-Item` `Get-ChildItem` командлеты или, записи не отображаются, так как они являются свойствами ключа, а не элементами или дочерними элементами.

Третья команда изменяет значение записи **NoOfEmployees** на 824.

Можно также использовать `New-ItemProperty` командлет для создания записи реестра и ее значения, а затем использовать `Set-ItemProperty` для изменения значения.

Для получения дополнительных сведений о `HKLM:` диске введите `Get-Help Get-PSDrive` .
Для получения дополнительных сведений об управлении реестром с помощью PowerShell введите `Get-Help Registry` .

### Пример 3. изменение элемента с помощью конвейера

Эти команды показывают, как использовать оператор конвейера ( `|` ) для отправки элемента в `Set-ItemProperty` .

Первая часть команды использует `Get-ChildItem` для получения объекта, представляющего файл "Weekly.txt". Команда использует оператор конвейера для отправки объекта File в `Set-ItemProperty` .
`Set-ItemProperty`Команда использует параметры **Name** и **value** для указания свойства и его нового значения.

Эта команда эквивалентна использованию параметра **InputObject** для указания объекта, который `Get-ChildItem` получает.

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

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

Задает фильтр для уточнения параметра **пути** . Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров. Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.

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

Заставляет командлет задать свойство для элементов, к которым пользователь не может получить доступ иным образом.
Применение этого параметра зависит от конкретного поставщика.
Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

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

### -InputObject

Указывает объект, содержащий свойства, которые изменяется этим командлетом.
Введите переменную, содержащую объект, либо команду, которая его возвращают.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к одному или нескольким расположениям. Значение **LiteralPath** используется точно так же, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Задает имя свойства.

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий свойство элемента.
По умолчанию этот командлет не создает выходные данные.

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

Указывает путь к элементам с изменяемым свойством.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Type

**Тип** — это динамический параметр, который поставщик реестра добавляет к `Set-ItemProperty` командлету.
Этот параметр работает только в дисках реестра.

Указывает тип свойства, добавляемого этим командлетом.
Допустимые значения для этого параметра:

- **Строка** : указывает строку, завершающуюся нулем. Эквивалентно **REG_SZ**.
- **Експандстринг** : указывает строку, завершающуюся нулем, которая содержит нерасширенные ссылки на переменные среды, развернутые при извлечении значения. Эквивалентно **REG_EXPAND_SZ**.
- **Двоичный** : Определяет двоичные данные в любой форме. Эквивалентно **REG_BINARY**.
- **DWORD** : задает 32-разрядное двоичное число. Эквивалентно **REG_DWORD**.
- **Многострочная** : указывает массив строк, заканчивающихся нулем, заканчивающихся двумя символами NULL.
  Эквивалентно **REG_MULTI_SZ**.
- **QWORD** : задает 64-разрядное двоичное число. Эквивалентно **REG_QWORD**.
- **Неизвестно** : указывает неподдерживаемый тип данных реестра, например **REG_RESOURCE_LIST**.

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value

Задает значение свойства.

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
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

### System.Management.Automation.PSObject

Вы можете передать объекты в этот командлет по конвейеру.

## Выходные данные

### Нет, System. Management. Automation. PSCustomObject

Этот командлет создает объект **PSCustomObject** , представляющий измененный элемент, и его новое значение, если указан параметр **PassThru** .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

`Set-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

