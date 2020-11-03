---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: f5bf1eab12b65b6e6ffeeb92c983777a576c503b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226597"
---
# Resume-Service

## Краткий обзор
Возобновляет одну или несколько приостановленных служб.

## SYNTAX

### InputObject (по умолчанию)

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### По умолчанию

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Resume-Service** отправляет сообщение о возобновлении в контроллер служб Windows для каждой из указанных служб.
Если служба приостановлена, она возобновляется.
Если в данный момент он выполняется, сообщение игнорируется.
Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр *InputObject* для передачи объекта службы, представляющего службы, которые требуется возобновить.

## Примеры

### Пример 1. Возобновление службы на локальном компьютере

```
PS C:\> Resume-Service "sens"
```

Эта команда возобновляет службу уведомлений о системных событиях на локальном компьютере.
Имя службы представлено в команде Сенс.
Команда использует параметр *Name* для указания имени службы службы, но команда пропускает имя параметра, так как имя параметра является необязательным.

### Пример 2. возобновление всех приостановленных служб

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

Эта команда возобновляет работу всех приостановленных служб на компьютере.
Команда Get-Service командлет возвращает все службы на компьютере.
Оператор конвейера (|) передает результаты в командлет Where-Object, который выбирает службы с приостановленным свойством **Status** .
Следующий оператор конвейера отправляет результаты в **Resume-Service** , что возобновляет работу приостановленных служб.

На практике можно использовать параметр *WhatIf* для определения эффекта от команды, перед тем как выполнять ее.

## PARAMETERS

### -DisplayName

Указывает отображаемые имена служб, которые нужно возобновить.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Exclude

Указывает службы, которые пропускает этот командлет.
Значение этого параметра определяет параметр *Name* .
Введите часть имени или шаблон, например "s*".
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

### -Include

Указывает службы для возобновления.
Значение этого параметра определяет параметр *Name* .
Введите часть имени или шаблон, например "s*".
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

### -InputObject

Указывает объекты **ServiceController** , представляющие службы, которые нужно возобновить.
Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имена служб, которые нужно возобновить.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий службу.
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

### System.ServiceProcess.ServiceController, System.String

В командлет можно передать по конвейеру объект службы или строку, содержащую имя службы.

## Выходные данные

### Нет или System.ServiceProcess.ServiceController

Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий возобновляемую службу, если указан параметр *PassThru* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Состояние приостановленных служб приостановлено. Когда службы возобновляются, их состояние выполняется.
* **Resume-Service** может управлять службами, только если у текущего пользователя есть разрешение на это. Если команда работает неправильно, возможно, у вас нет необходимых разрешений.
* Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`. Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .

## Связанные ссылки

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)

