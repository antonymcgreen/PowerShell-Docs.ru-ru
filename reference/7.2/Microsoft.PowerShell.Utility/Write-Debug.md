---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3d23f76dbf8e1c9a21805a4914038c8c4f319852
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603962"
---
# Write-Debug

## Краткий обзор
Выводит сообщение отладки на консоль.

## SYNTAX

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

`Write-Debug`Командлет записывает сообщения отладки на узел из скрипта или команды.

По умолчанию сообщения отладки не отображаются в консоли, но их можно отобразить с помощью параметра **отладки** или `$DebugPreference` переменной.

## Примеры

### Пример 1. понимание $DebugPreference

В этом примере записывается сообщение отладки.

```powershell
Write-Debug "Cannot open file."
```

Значение по умолчанию `$DebugPreference` — **SilentlyContinue**. Поэтому сообщение не отображается в консоли.

### Пример 2. изменение значения $DebugPreference

В этом примере показан результат изменения значения `$DebugPreference` переменной. Сначала мы отображаем текущее значение `$DebugPreference` и попытались написать сообщение отладки. Затем мы изменим значение `$DebugPreference` на **Continue**, что позволяет отображать сообщения отладки.

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

Дополнительные сведения о `$DebugPreference` см. в разделе [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).

### Пример 3. Переопределение $DebugPreference с помощью параметра Debug

`Test-Debug`Функция записывает значение `$DebugPreference` переменной в узел PowerShell и в поток отладки. В этом примере мы используем параметр **Debug** для переопределения `$DebugPreference` значения.

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

Обратите внимание, что `$DebugPreference` при использовании параметра **Debug** значение изменяется. Это изменение влияет только на область действия функции. Это значение не затрагивается за пределами функции.

Дополнительные сведения об общем параметре **Debug** см. в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## PARAMETERS

### -Message

Задает сообщение отладки для отправки на консоль.

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

Строку, содержащую сообщение отладки, можно передать в `Write-Debug` .

## Выходные данные

### None

`Write-Debug` выполняет запись только в поток отладки. Он не записывает никакие объекты в конвейер.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[О потоках вывода](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Error](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
