---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: 75b046ea6b11be3e4d87ed9db3e011a1f00d6ef5
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232774"
---
# Write-Output

## Краткий обзор
Отправляет указанные объекты в следующую команду по конвейеру. Если команда является последней в конвейере, объекты отображаются в консоли.

## SYNTAX

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## DESCRIPTION

`Write-Output`Командлет отправляет указанный объект по конвейеру в следующую команду.
Если команда является последней в конвейере, объект отображается в консоли.

`Write-Output` отправляет объекты в основной конвейер, также известный как "поток вывода" или "конвейер успешного выполнения". Чтобы отправить объекты ошибок в конвейер ошибок, используйте командлет Write-Error.

Этот командлет обычно используется в сценариях для отображения строк и других объектов в консоли. Один из встроенных псевдонимов для `Write-Output` — `echo` и аналогичен другим оболочкам, использующим `echo` , поведением по умолчанию является Отображение выходных данных в конце конвейера. В PowerShell, как правило, нет необходимости использовать командлет в экземплярах, где выходные данные отображаются по умолчанию. Например, выражение `Get-Process | Write-Output` будет эквивалентно `Get-Process`. Или, `echo "Home directory: $HOME"` может быть записано, `"Home directory: $HOME"` .

По умолчанию `Write-Output` перечисляет по коллекциям, предоставленным командлету. Однако `Write-Output` также можно использовать для передачи коллекций вниз по конвейеру в виде одного объекта с параметром **GetEnumerator** .

## Примеры

### Пример 1. Получение объектов и запись их на консоль

```powershell
$P = Get-Process
Write-Output $P
```

Первая команда получает процессы, запущенные на компьютере, и сохраняет их в `$P` переменной.

Вторая и третья команды отображают объекты процесса в `$P` консоли.

### Пример 2. Передача выходных данных другому командлету

```powershell
Write-Output "test output" | Get-Member
```

Эта команда передает строку "тестовый вывод" в `Get-Member` командлет, который отображает члены класса **System. String** , предказывая, что строка передается в конвейере.

### Пример 3. Отключение перечисления в выходных данных

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

Эта команда добавляет параметр **GetEnumerator** , чтобы обрабатывать коллекцию или массив как один объект через конвейер.

## PARAMETERS

### -InputObject

Задает объекты для отправки в конвейер. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Не перечислять

По умолчанию `Write-Output` командлет всегда перечисляет выходные данные. Параметр **GetEnumerator** подавляет поведение по умолчанию и предотвращает `Write-Output` перечисление выходных данных. Параметр **GetEnumerator** не действует, если команда заключена в круглые скобки, так как скобки принудительно перечисление. Например, `(Write-Output 1,2,3)` все равно перечисляет массив.

> [!NOTE]
> Этот параметр работает правильно только с PowerShell Core 6,2 и более поздними версиями. В более старых версиях PowerShell Core коллекция по-прежнему перечисляется даже при использовании этого параметра.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Вы можете передать объекты в `Write-Output` .

## Выходные данные

### System.Management.Automation.PSObject

`Write-Output` Возвращает объекты, которые передаются в качестве входных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Tee-Object](Tee-Object.md)

[Write-Debug](Write-Debug.md)

[Ошибка записи](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
