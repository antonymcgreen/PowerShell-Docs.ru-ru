---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: d3637825e7570e5fb0f3ff77efbc89e9d93974a3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227978"
---
# Move-Item

## Краткий обзор
Перемещает элемент из одного расположения в другое.

## SYNTAX

### Путь (по умолчанию)

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

### LiteralPath

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

## DESCRIPTION

`Move-Item`Командлет перемещает элемент, включая его свойства, содержимое и дочерние элементы, из одного расположения в другое.
Оба расположения должны поддерживаться одним и тем же поставщиком.
Например, файл или вложенный каталог можно переместить из одного каталога в другой, а подраздел реестра — из одного раздела в другой.
При перемещении элемент удаляется в исходном расположении и создается в новом.

## Примеры

### Пример 1. Перемещение файла в другой каталог и его переименование

Эта команда перемещает файл "Test.txt" с `C:` диска в каталог "е:\темп" и переименовывает его с "test.txt" на "tst.txt".

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### Пример 2. Перемещение каталога и его содержимого в другой каталог

Эта команда перемещает каталог C:\Temp и его содержимое в каталог "" C:\Logs "".
Каталог "Temp" и все его подкаталоги и файлы появятся в каталоге "Logs".

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### Пример 3. Перемещение всех файлов указанного расширения из текущего каталога в другой каталог

Эта команда перемещает все текстовые файлы ("*. txt") в текущем каталоге (представленной точкой (".")) в каталог "" C:\Logs "".

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### Пример 4. рекурсивное перемещение всех файлов указанного расширения из текущего каталога в другой каталог

Эта команда рекурсивно перемещает все текстовые файлы из текущего каталога и всех подкаталогов в каталог "К:\текстфилес".

Команда использует командлет, `Get-ChildItem` чтобы получить все дочерние элементы в текущем каталоге (представленном точкой \[ \] ) и его подкаталогах с *расширением txt. Он использует параметр **Recurse** рекурсии, чтобы получить рекурсивные значения и параметр Include, чтобы ограничить извлечение* файлами. txt.

Оператор конвейера ( `|` ) отправляет результаты этой команды в `Move-Item` , который перемещает текстовые файлы в каталог "Textfiles".

Если файлы, которые нужно переместить в "К:\текстфилес", имеют одинаковое имя, `Move-Item` выводит сообщение об ошибке и продолжается, но перемещает только один файл с каждым именем в "к:\текстфилес".
Другие файлы остаются в исходных каталогах.

Если каталог "Textfiles" (или любой другой элемент конечного пути) не существует, команда завершается ошибкой.
Отсутствующий каталог не создается, даже если используется параметр **Force** .
`Move-Item` перемещает первый элемент в файл с именем «Textfiles», а затем выводит сообщение об ошибке, объясняющее, что файл уже существует.

Кроме того, по умолчанию не `Get-ChildItem` перемещает скрытые файлы.
Чтобы переместить скрытые файлы, используйте параметр **Force** с `Get-ChildItem` .

Примечание. в Windows PowerShell 2,0 при использовании параметра **рекурсии** `Get-ChildItem` командлета значение параметра **path** должно быть контейнером.
Используйте параметр **include** , чтобы указать txt-файл для расширения имени файла ( `Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles` ).

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

### Пример 5. перемещение разделов и значений реестра в другой раздел

Эта команда перемещает разделы реестра и значения из раздела реестра MyCompany в "HKLM\Software" в раздел "Миневкомпани".
Подстановочный знак ("*") указывает, что необходимо переместить содержимое ключа "MyCompany", а не сам ключ.
В этой команде необязательные имена параметров **path** и **Destination** опускаются.

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### Пример 6. Перемещение каталога и его содержимого в подкаталог указанного каталога

Эта команда перемещает каталог " \[ logs \` 2006 \] " (и его содержимое) в каталог "Logs \[ 2006 \] ".

Параметр **LiteralPath** используется вместо **path** , так как имя исходного каталога включает открывающую и закрывающую квадратные скобки (" \[ " и " \] ").
Путь также заключается в одинарные кавычки (' '), поэтому символ обратного апострофа ( \` ) не интерпретируется правильно.

Параметру **назначения** не требуется путь к литералу, так как переменная назначения также должна быть заключена в одинарные кавычки, так как она содержит скобки, которые могут быть неверно интерпретированы.

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
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

### -Destination

Указывает путь к новому расположению элементов.
Значением по умолчанию является текущий каталог.
Знаки подстановки использовать можно, но в результате должно быть задано только одно расположение.

Чтобы переименовать перемещаемый элемент, укажите новое имя в значении параметра **Destination** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Exclude

Указывает в виде массива строк элемент или элементы, которые этот командлет исключает из операции.
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
Accept wildcard characters: True
```

### -Filter

Задает фильтр в формате или на языке поставщика.
Значение этого параметра определяет параметр **Path** .

Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.
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

Принудительное выполнение команды без запроса на подтверждение пользователем.
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

Указывает в виде массива строк элемент или элементы, которые этот командлет перемещает в операцию.
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
Accept wildcard characters: True
```

### -LiteralPath

Указывает путь к текущему расположению элементов.
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

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете.
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

Указывает путь к текущему расположению элементов.
Значением по умолчанию является текущий каталог.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
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

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь.

## Выходные данные

### Отсутствует или объект, представляющий перемещенный элемент.

При использовании параметра *PassThru* этот командлет создает объект, представляющий перемещенный элемент.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет переместит файлы между дисками, которые поддерживаются одним и тем же поставщиком, но переместит каталоги только в пределах одного диска.

Поскольку `Move-Item` команда перемещает свойства, содержимое и дочерние элементы элемента, все перемещения по умолчанию являются рекурсивными.

Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.
Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.
Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
