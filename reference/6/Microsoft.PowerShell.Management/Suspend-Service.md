---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 6e9fd5dd7a5736ef95976cb5195dd1d210d81651
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226785"
---
# Suspend-Service

## Краткий обзор
Приостанавливает одну или несколько запущенных служб.

## SYNTAX

### InputObject (по умолчанию)

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### По умолчанию

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Suspend-Service** отправляет сообщение о приостановке в контроллер служб Windows для каждой из указанных служб.
При приостановке служба все еще выполняется, но ее действие останавливается до возобновления, например с помощью командлета использовании Resume-Service.
Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр *InputObject* для передачи объекта службы, представляющего службы, которые необходимо приостановить.

## Примеры

### Пример 1. Приостановка службы

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

Эта команда приостанавливает службу Telnet (Tlntsvr) на локальном компьютере.

### Пример 2. Отображение того, что произойдет при приостановке служб

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

Эта команда сообщает, что произойдет, если вы приостановили службы с именем службы, которое начинается с LanMan.
Чтобы приостановить службы, выполните команду без параметра *WhatIf* .

### Пример 3. получение и приостановка службы

```
PS C:\> Get-Service schedule | Suspend-Service
```

Эта команда использует командлет **Get-Service** для получения объекта, представляющего планировщик задач (расписание) службы на компьютере.
Оператор конвейера (|) передает результат в **Suspend-Service** , который приостанавливает работу службы.

### Пример 4. Приостановка всех служб, которые могут быть приостановлены

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

Эта команда приостанавливает все службы на компьютере, которые можно приостановить.
Он использует **Get-Service** для получения объектов, представляющих службы на компьютере.
Оператор конвейера передает результаты в командлет Where-Object, который выбирает только службы со значением $True для свойства **CanPauseAndContinue** .
Другой оператор конвейера передает результаты в **Suspend-Service**.
Параметр *Confirm* запрашивает подтверждение перед приостановкой каждой службы.

## PARAMETERS

### -DisplayName

Указывает отображаемые имена приостанавливаемых служб.
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

Указывает службы, исключаемые из указанных служб.
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

Указывает службы для приостановки.
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

Указывает объекты **ServiceController** , представляющие службы для приостановки.
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

Указывает имена служб для приостановки.
Можно использовать подстановочные знаки.

Имя параметра является необязательным.
Можно использовать *имя* или его псевдоним, *ServiceName* , или можно опустить имя параметра.

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

Этот командлет создает объект **System. ServiceProcess. ServiceController** , представляющий службу, если указан параметр *PassThru* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* **Suspend-Service** может управлять службами, только если у текущего пользователя есть разрешение на это. Если команда работает неправильно, возможно, у вас нет необходимых разрешений.
* **Suspend-Service** может приостановить только службы, которые поддерживают приостановку и возобновление работы. Чтобы определить, можно ли приостановить конкретную службу, используйте командлет Get-Service вместе со свойством **CanPauseAndContinue** . Например, `Get-Service wmi | Format-List Name, CanPauseAndContinue`. Чтобы найти все службы на компьютере, которые можно приостановить, введите `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .
* Чтобы найти имена службы и отображаемые имена служб в системе, введите **Get-Service**. Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .

## Связанные ссылки

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Remove-Service](Remove-Service.md)
