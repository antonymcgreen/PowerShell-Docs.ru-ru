---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: dec5c2c905486110e4885f29d236ab41d945fb96
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601610"
---
# Rename-Item

## Краткий обзор
Переименовывает элемент в пространстве имен поставщика PowerShell.

## SYNTAX

### ByPath (по умолчанию)

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### ByLiteralPath

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## DESCRIPTION

`Rename-Item`Командлет изменяет имя указанного элемента. Он не влияет на содержимое переименовываемого элемента.

Нельзя использовать `Rename-Item` для перемещения элемента, например путем указания пути вместе с новым именем. Чтобы переместить и переименовать элемент, используйте `Move-Item` командлет.

## Примеры

### Пример 1. Переименование файла

Эта команда переименовывает файл `daily_file.txt` в `monday_file.txt` .

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### Пример 2. Переименование и перемещение элемента

Нельзя использовать `Rename-Item` для переименования и перемещения элемента. В частности, нельзя указывать путь для значения параметра **newname** , если путь не идентичен пути, указанному в параметре **path** . В противном случае допускается только новое имя.

В этом примере предпринимается попытка переименовать `project.txt` файл в текущем каталоге в `old-project.txt` в `D:\Archive` каталоге. Результатом является сообщение об ошибке в выходных данных.

```powershell
Rename-Item -Path "project.txt" -NewName "d:\archive\old-project.txt"
```

```Output
Rename-Item : can't rename because the target specified represents a path or device name.
At line:1 char:12
+ Rename-Item <<<<  -path project.txt -NewName d:\archive\old-project.txt
+ CategoryInfo          : InvalidArgument: (:) [Rename-Item], PS>  Move-Item -Path "project.txt" -De
stination "d:\archive\old-project.txt"
```

### Пример 3. Переименование раздела реестра

В этом примере раздел реестра переименовывается из **рекламы** в **маркетинг**. После выполнения команды раздел переименовывается, но записи реестра в нем остаются без изменений.

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### Пример 4. Переименование нескольких файлов

В этом примере все `*.txt` файлы в текущем каталоге переименованы в `*.log` .

```powershell
Get-ChildItem *.txt
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.TXT
-a----        10/3/2019   7:46 AM           2918 Monday.Txt
-a----        10/3/2019   7:47 AM           2918 Wednesday.txt
```

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace '.txt','.log' }
Get-ChildItem *.log
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.log
-a----        10/3/2019   7:46 AM           2918 Monday.log
-a----        10/3/2019   7:47 AM           2918 Wednesday.log
```

`Get-ChildItem`Командлет получает все файлы в текущей папке, `.txt` для которых расширение файла затем передает их `Rename-Item` . Значение **newname** — это блок скрипта, запускаемый перед отправкой значения в параметр **newname** .

В блоке скрипта `$_` Автоматическая переменная представляет каждый объект файла по мере того, как он доходит до команды через конвейер. Блок скрипта использует `-replace` оператор для замены расширения файла каждого файла на `.log` . Обратите внимание, что сопоставление с помощью `-replace` оператора не учитывает регистр.

## PARAMETERS

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell. Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

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

Заставляет командлет переименовывать элементы, которые в противном случае не могут быть изменены, например скрытые или только для чтения, а также псевдонимы или переменные только для чтения. Командлет не может изменить постоянные псевдонимы или переменные.
Применение этого параметра зависит от конкретного поставщика. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.

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

### -LiteralPath

Указывает путь к одному или нескольким расположениям. Значение **LiteralPath** используется точно так же, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewName

Задает новое имя элемента. Введите только имя без пути. Если ввести путь, отличающийся от пути, указанного в параметре **path** , `Rename-Item` выдает ошибку.
Чтобы переименовать и переместить элемент, используйте `Move-Item` .

В значении параметра **newname** нельзя использовать подстановочные знаки. Чтобы указать имя для нескольких файлов, используйте оператор **Replace** в регулярном выражении. Дополнительные сведения об операторе Replace см. в разделе [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент для конвейера. По умолчанию этот командлет не создает выходные данные.

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

Указывает путь к элементу для переименования.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь.

## Выходные данные

### Отсутствует или объект, представляющий переименованный элемент.

Этот командлет создает объект, представляющий переименованный элемент, если указан параметр **PassThru** . В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

`Rename-Item` предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

