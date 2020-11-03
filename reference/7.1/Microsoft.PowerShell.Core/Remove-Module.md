---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: f0fb0847d43a8fa8541ed194e474a1fab1f5ffa9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229174"
---
# Remove-Module

## Краткий обзор
Удаляет модули из текущего сеанса.

## SYNTAX

### name

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullyQualifiedName

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ModuleInfo

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Remove-Module** удаляет члены модуля, например командлеты и функции, из текущего сеанса.

Если модуль содержит сборку (DLL), все члены, реализованные в этой сборке, удаляются, но сборка не выгружается.

Командлет не деинсталлирует модуль и не удаляет его с компьютера.
Он влияет только на текущий сеанс PowerShell.

## Примеры

### Пример 1. Удаление модуля

```powershell
Remove-Module -Name "BitsTransfer"
```

Эта команда удаляет модуль BitsTransfer из текущего сеанса.

### Пример 2. Удаление всех модулей

```powershell
Get-Module | Remove-Module
```

Эта команда удаляет все модули из текущего сеанса.

### Пример 3. Удаление модулей с помощью конвейера

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

Эта команда удаляет модули BitsTransfer и PSDiagnostics из текущего сеанса.

Имена модулей отправляются в командлет **Remove-Module** с помощью конвейерного оператора (|).
Для получения подробной информации об удаляемых членах модуля используется общий параметр *Verbose*.

В *подробных* сообщениях отображаются элементы, которые были удалены.
Сообщения различаются, поскольку модуль BitsTransfer включает сборку, реализующую его командлеты, и вложенный модуль с его собственной сборкой.
Модуль PSDiagnostics включает файл скрипта модуля (PSM1), который экспортирует функции.

### Пример 4. Удаление модуля с помощью ModuleInfo

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

Эта команда использует параметр *ModuleInfo* для удаления модуля BitsTransfer.

## PARAMETERS

### -Force

Указывает, что этот командлет удаляет модули, которые доступны только для чтения.
По умолчанию командлет **Remove-Module** удаляет только модули, предназначенные и для чтения, и для записи.

Значения **ReadOnly** и **ReadWrite** хранятся в свойстве модуля **AccessMode**.

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

### -FullyQualifiedName

Указывает полные имена модулей для удаления.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ModuleInfo

Задает объекты модулей, которые нужно удалить.
Введите переменную, которая содержит объект модуля ( **PSModuleInfo** ), или команду, которая получает объект модуля, например команду Get-Module.
Объекты модулей можно также передать в командлет **Remove-Module** по конвейеру.

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Задает имена модулей, которые нужно удалить.
Можно использовать подстановочные знаки.
Строки с именами модулей можно также передать в командлет **Remove-Module** по конвейеру.

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
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

### System. String, System. Management. Automation. PSModuleInfo

Имена модулей и объекты модулей можно передать в командлет **Remove-Module**.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

При удалении модуля существует событие в модуле, который будет выполняться.
Это событие позволяет модулю реагировать на удаление и выполнять некоторую очистку, например освобождение ресурсов. Пример

$OnRemoveScript = {

  \# выполнить очистку

  $cachedSessions | Remove-PSSession

}

$ExecutionContext. sessionState. Module. Remove + = $OnRemoveScript

Для полной согласованности может также быть полезно реагировать на закрытие процесса PowerShell:

Register-EngineEvent-SourceIdentifier ([System. Management. Automation. Псенгинивент]:: завершение работы) — действие $OnRemoveScript

## Связанные ссылки

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

