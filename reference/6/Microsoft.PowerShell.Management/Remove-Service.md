---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: c55a7ef01171e63e8c64ee03446ca1bdcd838e2a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229134"
---
# Remove-Service

## Краткий обзор
Удаляет службу Windows.

## SYNTAX

### Имя (по умолчанию)

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Remove-Service`Командлет удаляет службу Windows в реестре и в базе данных службы.

`Remove-Service`Командлет был представлен в PowerShell 6,0.

## Примеры

### Пример 1. Удаление службы

Это приведет к удалению службы с именем TestService.

```powershell
Remove-Service -Name "TestService"
```

### Пример 2. Удаление службы с помощью отображаемого имени

В этом примере удаляется служба с именем TestService. Команда использует `Get-Service` для получения объекта, представляющего службу TestService, с помощью отображаемого имени. Оператор конвейера ( `|` ) передает объект в `Remove-Service` , который удаляет службу.

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## PARAMETERS

### -InputObject

Указывает объекты **ServiceController** , представляющие удаляемые службы. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имена служб для удаления. Можно использовать подстановочные знаки.

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

### Нет

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .

## Связанные ссылки

[Get-Service](Get-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
