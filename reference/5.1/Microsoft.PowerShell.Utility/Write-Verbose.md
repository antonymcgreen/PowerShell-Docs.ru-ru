---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: e16e002ab9e803900712542c329723f6a44a880f
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232810"
---
# Write-Verbose

## Краткий обзор
Записывает текст в поток подробных сообщений.

## SYNTAX

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

`Write-Verbose`Командлет записывает текст в поток подробных сообщений в PowerShell. Как правило, поток подробных сообщений используется для предоставления более подробных сведений об обработке команд.

По умолчанию поток подробных сообщений не отображается, но его можно отобразить, изменив значение `$VerbosePreference` переменной или используя параметр **verbose** Common в любой команде.

## Примеры

### Пример 1. запись сообщения о состоянии

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

Эти команды используют `Write-Verbose` командлет для вывода сообщения о состоянии. По умолчанию это сообщение не отображается.

Вторая команда использует параметр **verbose** Common, который отображает все подробные сообщения, независимо от значения `$VerbosePreference` переменной.

### Пример 2. Настройка $VerbosePreference и запись сообщения о состоянии

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

Эти команды используют `Write-Verbose` командлет для вывода сообщения о состоянии. По умолчанию это сообщение не отображается.

Первая команда присваивает значение Continue `$VerbosePreference` переменной предпочтения. Значение по умолчанию, `SilentlyContinue` , подавляет подробные сообщения. Вторая команда записывает подробное сообщение.

## PARAMETERS

### -Message

Задает отображаемое сообщение. Этот параметр обязателен. Можно также передать строку сообщения в `Write-Verbose` .

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

Строку, содержащую сообщение, можно передать в конвейер `Write-Verbose` .

## Выходные данные

### Нет

`Write-Verbose` выполняет запись только в поток подробных сообщений.

## ПРИМЕЧАНИЯ

- Подробные сообщения возвращаются только в том случае, если в команде используется общий параметр **Verbose**. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).
- В фоновых заданиях и удаленных командах Windows PowerShell `$VerbosePreference` переменная в сеансе задания и удаленный сеанс определяют, отображается ли подробное сообщение по умолчанию.
  Дополнительные сведения о `$VerbosePreference` переменной см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

## Связанные ссылки

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Ошибка записи](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Warning](Write-Warning.md)
