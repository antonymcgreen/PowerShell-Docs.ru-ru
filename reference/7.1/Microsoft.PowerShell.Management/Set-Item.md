---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Item
ms.openlocfilehash: 5fbdb8345f0d8a1e83a40dbbad2e26fd89960f1d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226753"
---
# Set-Item

## Краткий обзор
Изменяет значение элемента на значение, указанное в команде.

## SYNTAX

### Путь (по умолчанию)

```
Set-Item [-Path] <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Set-Item -LiteralPath <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Item`Командлет изменяет значение элемента, например переменную или раздел реестра, на значение, указанное в команде.

## Примеры

### Пример 1. Создание псевдонима

Эта команда создает псевдоним NP для блокнота.

```powershell
Set-Item -Path alias:np -Value "c:\windows\notepad.exe"
```

### Пример 2. изменение значения переменной среды

Эта команда изменяет значение переменной среды UserRole на "Администратор".

```powershell
Set-Item -Path env:UserRole -Value "Administrator"
```

### Пример 3. изменение функции Prompt

Эта команда изменяет функцию Prompt таким образом, чтобы она отображала время перед путем.

```powershell
Set-Item -Path function:prompt -Value {'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '}
```

### Пример 4. Задание параметров для функции Prompt

Эта команда задает параметры **AllScope** и **ReadOnly** для функции Prompt.
Эта команда использует динамический параметр **Options функции** `Set-Item` .
Параметр **Options** доступен `Set-Item` только в том случае, если он используется с **псевдонимом** или поставщиком **функций** .

```powershell
Set-Item -Path function:prompt -Options "AllScope,ReadOnly"
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

Заставляет командлет задавать элементы, которые в противном случае не могут быть изменены, например псевдоним или переменные только для чтения. С помощью этого командлета нельзя изменять постоянные псевдонимы или переменные.
Применение этого параметра зависит от конкретного поставщика.
Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
Даже при использовании параметра *Force* командлет не может переопределять ограничения безопасности.

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

### -PassThru

Передает объект, представляющий элемент, в конвейер.
По умолчанию этот командлет не создает выходные данные.

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

Задает путь к расположению элементов.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Value

Задает новое имя для элемента.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

Объект, который представляет новое значение элемента, можно передать этому командлету по конвейеру.

## Выходные данные

### Отсутствует или объект, представляющий новый или измененный элемент.

Этот командлет создает объект, который представляет элемент, если указан параметр *PassThru* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- `Set-Item` не поддерживается поставщиком файловой системы PowerShell. Чтобы изменить значения элементов в файловой системе, используйте `Set-Content` командлет.
- На дисках реестра `HKLM:` и `HKCU:` `Set-Item` изменяет данные в значении (по умолчанию) раздела реестра.
  - Чтобы создать и изменить имена разделов реестра, используйте `New-Item` `Rename-Item` командлет и.
  - Чтобы изменить имена и данные в значениях реестра, используйте `New-ItemProperty` `Set-ItemProperty` командлеты, и `Rename-ItemProperty` .
- `Set-Item` предназначен для работы с данными, предоставляемыми любым поставщиком.
  Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.
  Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

