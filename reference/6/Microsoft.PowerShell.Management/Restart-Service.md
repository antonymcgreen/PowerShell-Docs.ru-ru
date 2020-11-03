---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: edbe7f93a3bef4b82adbba6b8a39b761fa54c28e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226817"
---
# Restart-Service

## Краткий обзор
Перезапускает одну или несколько служб.

## SYNTAX

### InputObject (по умолчанию)

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### По умолчанию

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DisplayName

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Restart-Service** отправляет сообщение об ошибке, а затем начальное сообщение в контроллер служб Windows для указанной службы.
Если служба уже остановлена, она запускается без уведомления об ошибке.
Службы можно указать по именам служб или отображаемым именам, либо можно использовать параметр *InputObject* для передачи объекта, представляющего каждую службу, которую требуется перезапустить.

## Примеры

### Пример 1. Перезапуск службы на локальном компьютере

```powershell
PS C:\> Restart-Service -Name winmgmt
```

Эта команда перезапускает службу инструментария управления Windows (WinMgmt) на локальном компьютере.

### Пример 2. Исключение службы

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

Эта команда перезапускает службы с отображаемым именем, которое начинается с Net, за исключением службы Net Logon.

### Пример 3. Запуск всех остановленных сетевых служб

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

Эта команда запускает все остановленные сетевые службы на компьютере.

Она использует командлет Get-Service для получения объектов, представляющих службы, имена которых начинаются с net.
Конвейерный оператор (|) отправляет объект служб в командлет Where-Object, который выбирает только службы с состоянием "Остановлена".
Другой конвейерный оператор отправляет выбранные службы в **Restart-Service**.

На практике можно использовать параметр *WhatIf* для определения эффекта от команды, перед тем как выполнять ее.

## PARAMETERS

### -DisplayName

Указывает отображаемые имена перезапускаемых служб.
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

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

Указывает службы, Перезапускаемые этим командлетом.
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

Указывает объекты **ServiceController** , представляющие службы для перезапуска.
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

Указывает имена перезапускаемых служб.

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

При указании параметра *PassThru* этот командлет создает объект **System.ServiceProcess.ServiceController** , представляющий перезапускаемую службу.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* **Restart-Service** может управлять службами, только когда у текущего пользователя есть соответствующие разрешения. Если команда работает неправильно, возможно, у вас нет необходимых разрешений.
* Чтобы найти имена службы и отображаемые имена служб в системе, введите команду **Get-Service**. Имена служб отображаются в столбце **имя** , а отображаемые имена отображаются в столбце **DisplayName** .

## Связанные ссылки

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
