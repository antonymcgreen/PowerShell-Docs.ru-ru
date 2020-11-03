---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 2ae91494b87b9c4cce13d1a41bcbce72405cd0dd
ms.sourcegitcommit: 69b08b28ee2ef3168065672a23b9b6f0c578c95b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "93230597"
---
# Stop-Service

## Краткий обзор
Останавливает одну или несколько запущенных служб.

## SYNTAX

### InputObject (по умолчанию)

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### По умолчанию

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayName

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **останавливает-Service** отправляет сообщение об ошибке в контроллер служб Windows для каждой из указанных служб.
Службы можно указать по их именам служб или отображаемым именам. также можно использовать параметр **InputObject** для передачи объекта службы, представляющего службу, которую необходимо отключить.

## Примеры

### Пример 1. Завершение службы на локальном компьютере

```
PS C:\> Stop-Service -Name "sysmonlog"
```

Эта команда останавливает службы журналов производительности и оповещений (SysmonLog) на локальном компьютере.

### Пример 2. Завершение службы с помощью отображаемого имени

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

Эта команда останавливает службу Telnet на локальном компьютере.
Команда использует **Get-Service** для получения объекта, представляющего службу Telnet.
Оператор конвейера (|) передает объект в **Stop-Service** , который останавливает службу.

### Пример 3. Завершение службы, имеющей зависимые службы

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

В этом примере останавливается служба IISAdmin на локальном компьютере.
Поскольку остановка этой службы также останавливает службы, зависящие от службы IISAdmin, лучше перед **остановкой службы** выполнить команду, в которой перечислены службы, зависящие от службы IISAdmin.

Первая команда указывает службы, зависимые от IISAdmin.
Он использует **Get-Service** для получения объекта, представляющего службу IISAdmin.
Оператор конвейера (|) передает результат в командлет Format-List.
Команда использует параметр *Property* командлета **Format-List** для вывода списка только свойств **Name** и **DependentServices** службы.

Вторая команда останавливает службу IISAdmin.
Параметр *Force* необходим для того, чтобы служба, имеющая зависимые службы, была остановлена.
Команда использует параметр *Confirm* для запроса подтверждения от пользователя перед остановкой каждой службы.

## PARAMETERS

### -DisplayName

Указывает отображаемые имена останавливаемых служб.
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

### -Force

Заставляет командлет прекращать работу службы, даже если она зависит от служб.

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

### -Include

Указывает службы, которые останавливаются этим командлетом.
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

Указывает объекты **ServiceController** , представляющие останавливаемые службы.
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

Указывает имена служб для отмены.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Неожидание

Указывает, что этот командлет использует параметр No Wait.

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

В этот командлет можно передать объект службы или строку, содержащую имя службы.

## Выходные данные

### Нет или System.ServiceProcess.ServiceController

Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, при использовании параметра *PassThru* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Можно также обратиться к командлету " **останавливаюте службы** " по встроенному псевдониму **СПСВ** . Подробнее см. в разделе "about_Aliases".

  **Служба останавливает-Service** может управлять службами только в том случае, если у текущего пользователя есть разрешение на это.
Если команда работает неправильно, возможно, у вас нет необходимых разрешений.

  Чтобы найти имена служб и отображаемые имена в системе, введите `Get-Service`.
Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .


## Связанные ссылки

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
