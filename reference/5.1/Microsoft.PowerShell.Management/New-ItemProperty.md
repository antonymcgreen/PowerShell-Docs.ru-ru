---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 2569f4778f54f6cdad22e10cf92e727b73c323e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227970"
---
# New-ItemProperty

## Краткий обзор
Создает новое свойство для элемента и задает его значение.

## SYNTAX

### Путь (по умолчанию)

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

`New-ItemProperty`Командлет создает новое свойство для указанного элемента и задает его значение.
Как правило, этот командлет используется для создания новых значений реестра, так как значения реестра являются свойствами элемента раздела реестра.

Этот командлет не добавляет свойства в объект.

- Чтобы добавить свойство в экземпляр объекта, используйте `Add-Member` командлет.
- Чтобы добавить свойство ко всем объектам определенного типа, измените Types.ps1XML-файл.

## Примеры

### Пример 1. Добавление записи реестра

Эта команда добавляет новую запись реестра «NoOfEmployees» в раздел «MyCompany» раздела «HKLM: \ Software Hive».

Первая команда использует параметр **path** для указания пути к разделу реестра MyCompany.
Он использует параметр **Name** для указания имени записи, а параметр **value** — для указания его значения.

Вторая команда использует `Get-ItemProperty` командлет для просмотра новой записи реестра.

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### Пример 2. Добавление записи реестра в раздел

Эта команда добавляет новую запись реестра в раздел реестра. Чтобы указать ключ, он использует оператор конвейера (|) для отправки объекта, представляющего ключ `New-ItemProperty` .

Первая часть команды использует `Get-Item` командлет для получения раздела реестра MyCompany. Оператор конвейера отправляет результаты команды в `New-ItemProperty` , который добавляет новую запись реестра ("нуфлокатионс") и ее значение (3) к ключу "MyCompany".

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

Эта команда работает, так как функция привязки параметров Windows PowerShell связывает путь `RegistryKey` объекта, `Get-Item` возвращаемого с параметром **LiteralPath** `New-ItemProperty` . Дополнительные сведения см. в разделе [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).

### Пример 3. Создание многострочного значения в реестре с помощью Here-String

В этом примере создается многострочное значение с помощью строки here.

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### Пример 4. Создание многострочного значения в реестре с помощью массива

В примере показано, как использовать массив значений для создания `MultiString` значения.

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## PARAMETERS

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия.
По умолчанию используется текущий пользователь.

Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

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

Указывает свойство или свойства, исключаемые этим командлетом из операции, в виде массива строк.
Значение этого параметра определяет параметр **Path** .
Введите путь к элементу или шаблон, например. «*.txt».
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

Задает фильтр в формате или на языке поставщика.
Значение этого параметра определяет параметр **Path** .

Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика. Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Заставляет командлет создать свойство объекта, доступ к которому в противном случае невозможен для пользователя.
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

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.
Значение этого параметра определяет параметр **Path** .
Введите путь к элементу или шаблон, например. «*.txt».
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к текущему расположению свойства.
В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.
Никакие символы не интерпретируются как знаки подстановки.
Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

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

### -Name

Задает имя для нового свойства.
Если свойство является записью реестра, этот параметр задает имя записи.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь к элементу.
Этот параметр определяет элемент, к которому этот командлет добавляет новое свойство.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertyType

Указывает тип свойства, добавляемого этим командлетом.
Допустимые значения для этого параметра:

- **Строка** : указывает строку, завершающуюся нулем. Эквивалентно **REG_SZ** .
- **Експандстринг** : указывает строку, завершающуюся нулем, которая содержит нерасширенные ссылки на переменные среды, развернутые при извлечении значения. Эквивалентно **REG_EXPAND_SZ** .
- **Двоичный** : Определяет двоичные данные в любой форме. Эквивалентно **REG_BINARY** .
- **DWORD** : задает 32-разрядное двоичное число. Эквивалентно **REG_DWORD** .
- **Многострочная** : указывает массив строк, заканчивающихся нулем, заканчивающихся двумя символами NULL.
  Эквивалентно **REG_MULTI_SZ** .
- **QWORD** : задает 64-разрядное двоичное число. Эквивалентно **REG_QWORD** .
- **Неизвестно** : указывает неподдерживаемый тип данных реестра, например **REG_RESOURCE_LIST** .

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

### -UseTransaction

Включает команду в активную транзакцию.
Этот параметр доступен только при выполнении транзакции.
Дополнительные сведения см. в разделе about_Transactions.

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

Задает значение свойства.
Если свойство является записью реестра, этот параметр указывает значение записи.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. PSCustomObject

`New-ItemProperty` Возвращает пользовательский объект, содержащий новое свойство.

## ПРИМЕЧАНИЯ

`New-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
