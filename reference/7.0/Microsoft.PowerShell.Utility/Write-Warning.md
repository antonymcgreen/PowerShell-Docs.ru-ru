---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: dde8e497159e3e9a7bf63010bc12566d68d8de0f
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232881"
---
# Write-Warning

## Краткий обзор
Записывает предупреждающее сообщение.

## SYNTAX

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

`Write-Warning`Командлет Записывает предупреждающее сообщение на узел PowerShell. Ответ на предупреждение зависит от значения `$WarningPreference` переменной пользователя и использования общего параметра **WarningAction** .

## Примеры

### Пример 1. Написание предупреждающего сообщения

Эта команда выводит сообщение "предупреждение: это только предупреждение теста".

```powershell
Write-Warning "This is only a test warning."
```

### Пример 2. Передача строки в Write-Warning

Эта команда показывает, что можно использовать оператор конвейера ( `|` ) для отправки строки в `Write-Warning` .
Можно сохранить строку в переменной, как показано в этой команде, или передать строку непосредственно в `Write-Warning` .

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### Пример 3. задание переменной $WarningPreference и запись предупреждения

В этом примере показано воздействие значения `$WarningPreference` переменной на `Write-Warning` команду.

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

Первая команда отображает значение по умолчанию для `$WarningPreference` переменной, то есть `Continue` . В результате при записи предупреждения отображается предупреждающее сообщение и продолжается выполнение команды.

При изменении значения `$WarningPreference` переменной результат `Write-Warning` команды снова изменяется. Значение `SilentlyContinue` подавляет вывод предупреждения. Значение `Stop` отображает предупреждение, а затем останавливает выполнение команды.

Дополнительные сведения о `$WarningPreference` переменной см. в разделе [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).

### Пример 4. Установка параметра WarningAction и запись предупреждения

В этом примере показан результат использования общего параметра **WarningAction** в `Write-Warning` команде. Вы можете использовать общий параметр **WarningAction** с любым командлетом, чтобы определить, как PowerShell реагирует на предупреждения, полученные от этой команды. Общий параметр **WarningAction** переопределяет значение `$WarningPreference` только для этой конкретной команды.

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

Эта команда использует `Write-Warning` командлет для вывода предупреждения. Общий параметр **WarningAction** со значением "запрос" направляет систему на запрос пользователя, когда команда выводит предупреждение.

Дополнительные сведения об общем параметре **WarningAction** см. в разделе [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).

## PARAMETERS

### -Message
Указывает предупреждающее сообщение.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку, содержащую предупреждение, можно передать в `Write-Warning` .

## Выходные данные

### Нет

`Write-Warning` выполняет запись только в поток предупреждений. Он не формирует каких-либо других выходных данных.

## ПРИМЕЧАНИЯ

Значением по умолчанию для `$WarningPreference` переменной является `Continue` , которое отображает предупреждение и затем возобновляет выполнение команды. Чтобы определить допустимые значения для привилегированной переменной, например `$WarningPreference` , задайте для нее строку случайных символов, например "ABC". В итоговом сообщении об ошибке выводится список допустимых значений.

## Связанные ссылки

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Ошибка записи](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)
