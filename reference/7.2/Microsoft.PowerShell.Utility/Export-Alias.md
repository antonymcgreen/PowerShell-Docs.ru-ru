---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 9da204513ed4a17eb8dc20481b878a4a783534f6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601881"
---
# Export-Alias

## Краткий обзор
Экспортирует сведения об определенных на текущий момент псевдонимах в файл.

## SYNTAX

### ByPath (по умолчанию)

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Export-Alias`Командлет экспортирует псевдонимы в текущем сеансе в файл.
Если файл вывода не существует, командлет его создаст.

`Export-Alias` может экспортировать псевдонимы в определенной области или во всех областях, они могут создавать данные в формате CSV или в виде серии Set-Alias команд, которые можно добавить в сеанс или в профиль PowerShell.

## Примеры

### Пример 1. экспорт псевдонима

```powershell
Export-Alias -Path "alias.csv"
```

Эта команда экспортирует текущие сведения о псевдонимах в файл Alias.csv, находящийся в текущем каталоге.

### Пример 2. экспорт псевдонима, если файл экспорта уже не существует

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

Эта команда экспортирует псевдонимы текущего сеанса в файл Alias.csv.

Так как указан параметр **NoClobber** , команда завершится ошибкой, если файл Alias.csv уже существует в текущем каталоге.

### Пример 3. Добавление псевдонимов в файл

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

Эта команда добавляет псевдонимы текущего сеанса в файл Alias.csv.

Команда использует параметр **Description** для добавления описания к комментариям в верхней части файла.

Команда также использует параметр **Force** для перезаписи существующих файлов Alias.csv, даже если они имеют атрибут «только для чтения».

### Пример 4. экспорт псевдонимов в качестве скрипта

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

В этом примере показано, как использовать формат файла скрипта, который `Export-Alias` создает.

Первая команда экспортирует псевдонимы текущего сеанса в файл Alias.ps1.
Для создания файла, содержащего команду Set-Alias для каждого псевдонима, используется параметр **as** со значением скрипта.

Вторая команда добавляет псевдонимы из файла Alias.ps1 к профилю CurrentUser-CurrentHost.
Путь к профилю сохраняется в `$Profile` переменной.
Команда использует `Get-Content` командлет для получения псевдонимов из файла Alias.ps1 и `Add-Content` командлета, чтобы добавить их в профиль.
Дополнительные сведения см. в разделе about_Profiles.

Третья и четвертая команды добавляют псевдонимы в файл Alias.ps1 в удаленный сеанс на компьютере Server01.
Третья команда использует `New-PSSession` командлет для создания сеанса.
Четвертая команда использует параметр **FilePath** `Invoke-Command` командлета для запуска файла Alias.ps1 в новом сеансе.

## PARAMETERS

### — Добавление

Указывает, что этот командлет добавляет выходные данные в указанный файл вместо перезаписи существующего содержимого этого файла.

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

### — Как

Задает формат выходных данных.
По умолчанию используется формат CSV.
Допустимые значения для этого параметра:

- CSV.
формат значений, разделенных запятыми (CSV).
- Скрипт.
Создает `Set-Alias` команду для каждого экспортированного псевдонима.
Если выходной файл имеет расширение PS1, его можно запускать в качестве скрипта для добавления псевдонимов к любому сеансу.

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Задает описание экспортируемого файла.
Описание добавляется в виде комментария в начало файла после заголовка.

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

Принудительное выполнение команды без запроса на подтверждение пользователем.

Перезаписывает выходной файл, даже если для него установлен атрибут «только для чтения».

По умолчанию `Export-Alias` перезаписывает файлы без предупреждения, если только атрибут "только для чтения" или "скрытый" не задан, либо в команде используется параметр **NoClobber** .
Параметр **NoClobber** имеет приоритет над параметром **Force** , если оба используются в команде.

Параметр **Force** не может принудительно `Export-Alias` перезаписать файлы с атрибутом Hidden.

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

### -LiteralPath

Указывает путь к выходному файлу.
В отличие от параметра **Path**, значение параметра **LiteralPath** используется в точности так, как вводится.
Никакие символы не интерпретируются как знаки подстановки.
Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

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

### -Name

Задает имена в виде массива псевдонимов для экспорта.
Разрешено использовать подстановочные знаки.

По умолчанию `Export-Alias` экспортирует все псевдонимы в сеансе или области.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoClobber

Указывает, что этот командлет не позволяет `Export-Alias` перезаписывать какие-либо файлы, даже если в команде используется параметр **Force** .

Если параметр **NoClobber** опущен, `Export-Alias` будет перезаписан существующий файл без предупреждения, если только для этого файла не задан атрибут «только для чтения».
*NoClobber* имеет приоритет над параметром **Force** , который позволяет `Export-Alias` перезаписывать файл с атрибутом только для чтения.

*NoClobber* не запрещает параметру **append** добавлять содержимое в существующий файл.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к выходному файлу.
Знаки подстановки использовать можно, но итоговое значение пути должно указывать только на одно имя файла.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Scope

Задает область, из которой должны быть экспортированы псевдонимы.
Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Скрипт
- Число относительно текущей области (от 0 до количества областей, где 0 является текущей областью, а 1 — ее родителем)

По умолчанию используется значение Local.
Дополнительные сведения см. в разделе about_Scopes.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Отсутствует.

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### None или System. Management. Automation. AliasInfo

При использовании параметра **PassThru** `Export-Alias` возвращает объект **System. Management. Automation. AliasInfo** , представляющий псевдоним.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Командлет Export-Alias можно применять только для экспорта в файл.

## Связанные ссылки

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

