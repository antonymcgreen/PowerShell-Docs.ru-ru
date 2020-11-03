---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226694"
---
# Export-Console

## Краткий обзор
Экспортирует имена оснасток в текущем сеансе в файл консоли.

## SYNTAX

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Export-Console** экспортирует имена оснасток Windows PowerShell в текущем сеансе в файл консоли Windows PowerShell (. psc1).
Можно использовать этот командлет, чтобы сохранить оснастки для использования в последующих сеансах.

Чтобы добавить оснастки в файл консоли. psc1 в сеанс, запустите Windows PowerShell (Powershell.exe) в командной строке с помощью Cmd.exe или другого сеанса Windows PowerShell, а затем используйте параметр *PSConsoleFile* в Powershell.exe, чтобы указать файл консоли.

Дополнительные сведения об оснастках Windows PowerShell см. в разделе about_PSSnapins.

## Примеры

### Пример 1. экспорт имен оснасток в текущем сеансе

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

Эта команда экспортирует имена оснасток Windows PowerShell в текущем сеансе в файл ConsoleS1. psc1 в папке консолей установочной папки Windows PowerShell $pshome.

### Пример 2. экспорт имен оснасток в самый последний файл консоли

```
PS C:\> Export-Console
```

Эта команда экспортирует имена оснасток Windows PowerShell из текущего сеанса в файл консоли Windows PowerShell, который использовался в текущем сеансе последним.
Содержимое файла перезаписывается.

Если экспорт файла консоли в текущем сеансе не производился, пользователю предлагается подтвердить выполнение команды, а затем ввести имя файла.

### Пример 3. Добавление оснастки и экспорт имен оснасток

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

Эти команды добавляют новую оснастку Windows PowerShell NewPSSnapin в текущий сеанс, экспортируют имена оснасток Windows PowerShell в текущем сеансе в файл консоли и запускают сеанс Windows PowerShell с использованием файла консоли.

Первая команда добавляет оснастку NewPSSnapin к текущему сеансу с помощью командлета **Add-PSSnapin** .
Добавлять можно только те оснастки Windows PowerShell, которые зарегистрированы в данной системе.

Вторая команда экспортирует имена оснасток Windows PowerShell в файл NewPSSnapinConsole.psc1.

Третья команда запускает Windows PowerShell с использованием файла NewPSSnapinConsole.psc1.
Поскольку файл консоли включает имя оснастки Windows PowerShell, в текущем сеансе можно использовать командлеты и поставщики, которые поддерживаются оснасткой.

### Пример 4. экспорт имен оснасток в указанное расположение

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

Эта команда экспортирует имена оснасток Windows PowerShell в текущем сеансе в файл Console01.psc1 в текущем каталоге.

Вторая команда отображает содержимое файла Console01.psc1 в Блокноте.

### Пример 5. Определение файла консоли для обновления

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

В этом примере показано, как использовать автоматическую переменную $ConsoleFileName для определения файла консоли, который будет обновлен при использовании командлета **Export-Console** без значения параметра *path* .

Первая команда использует параметр *PSConsoleFile* PowerShell.exe, чтобы открыть Windows PowerShell с помощью файла Console01. psc1.

Вторая команда использует командлет **Add-PSSnapin** для добавления оснастки Миснапин Windows PowerShell к текущему сеансу.

Третья команда использует командлет **Export-Console** для экспорта имен всех оснасток Windows PowerShell в сеансе в файл невконсоле. psc1.

Четвертая команда отображает переменную $ConsoleFileName.
Он содержит последний использовавшийся файл консоли.
Пример выходных данных показывает, что последним использовался файл NewConsole.ps1.

Пятая команда добавляет в текущую консоль оснастку SnapIn03.

Шестая команда использует командлет **Export-Console** без параметра *path* .
Эта команда экспортирует имена всех Windows PowerShell оснасток в текущем сеансе в последний использованный файл (в данном случае NewConsole.psc1).

## PARAMETERS

### -Force
Указывает, что этот командлет перезаписывает данные в файле консоли без предупреждения, даже если файл имеет атрибут "только для чтения".
Атрибут только для чтения изменяется и не сбрасывается после завершения команды.

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

### -NoClobber
Указывает, что этот командлет не перезаписывает существующий файл консоли.
По умолчанию, если файл выполняется по указанному пути, **Export-Console** перезаписывает файл без предупреждения.

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

### -Path
Определяет путь и имя файла для файла консоли (*.psc1).
Введите необязательный путь и имя.
Подстановочные знаки не допускаются.

Если указано только имя файла, **Export-Console** создает файл с таким именем и расширением имени файла PSC1 в текущем каталоге.

Этот параметр является обязательным, если вы не открывали Windows PowerShell с параметром *PSConsoleFile* или не экспортировали файл консоли во время текущего сеанса.
Он также необходим при использовании параметра *NoClobber* , чтобы предотвратить перезапись текущего файла консоли.

Если этот параметр не указан, **Export-Console** перезаписывает файл консоли, который использовался в последнее время в этом сеансе.
Путь к последнему используемому файлу консоли хранится в значении автоматической переменной $ConsoleFileName.
Дополнительные сведения см. в разделе about_Automatic_Variables.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
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
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String
Строку пути можно передать в этот командлет по конвейеру.

## Выходные данные

### System. IO. FileInfo
Этот командлет создает файл, содержащий экспортированные псевдонимы.

## ПРИМЕЧАНИЯ

* Если файл консоли (PSC1) используется для запуска сеанса, имя этого файла автоматически сохраняются в автоматической переменной $ConsoleFileName. Значение $ConsoleFileName обновляется при использовании параметра *path* командлета **Export-Console** для указания нового файла консоли. Если файл консоли не используется, $ConsoleFileName не имеет значения ($Null).

  Чтобы использовать файл консоли Windows PowerShell в новом сеансе, запустите Windows PowerShell с помощью следующего синтаксиса:

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  Оснастки Windows PowerShell можно также сохранить для будущих сеансов, добавив команду Add-PSSnapin в профиль Windows PowerShell.
Дополнительные сведения см. в разделе about_Profiles.


## Связанные ссылки

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
