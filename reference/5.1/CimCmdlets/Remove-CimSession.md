---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: f53d0003e915234b00cad12b7f6bbeef0a263558
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226878"
---
# Remove-CimSession

## Краткий обзор
Удаляет один или несколько сеансов CIM.

## SYNTAX

### Цимсессионсет (по умолчанию)

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### компутернамесет

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SessionId

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### инстанцеидсет

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Имя

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Remove-CimSession`Командлет удаляет один или несколько объектов сеанса CIM из локального сеанса PowerShell.

## Примеры

### Пример 1. Удаление всех сеансов CIM

Этот пример извлекает все доступные сеансы CIM на локальном компьютере с помощью командлета [Get-CimSession](Get-CimSession.md) , а затем удаляет их с помощью `Remove-CimSession` .

```powershell
Get-CimSession | Remove-CimSession
```

### Пример 2. удаление конкретного сеанса CIM

В этом примере удаляется сеанс CIM, имеющий значение **ID** , равное 5.

```powershell
Remove-CimSession -Id 5
```

### Пример 3. Отображение списка сеансов CIM для удаления с помощью параметра WhatIf

В этом примере используется общий параметр **WhatIf** для указания на то, что удаление не должно выполняться, но при этом выводятся только те данные, которые были бы выполнены.

```powershell
Remove-CimSession -Name a* -WhatIf
```

## PARAMETERS

### -CimSession

Указывает объекты сеанса для закрытия сеансов CIM.

Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) командлеты или.
Дополнительные сведения см. в разделе [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ComputerName

Указывает массив имен компьютеров. Удаляет сеансы, подключающиеся к указанным компьютерам. Можно указать полное доменное имя или NetBIOS-имя.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Id

Указывает идентификатор удаляемого сеанса CIM. Укажите один или несколько идентификаторов, разделенных запятыми, или используйте оператор Range ( `..` ), чтобы указать диапазон идентификаторов. **Идентификатор** — это целое число, которое однозначно определяет сеанс CIM в текущем сеансе PowerShell.

Дополнительные сведения об операторе Range см. в разделе [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).

```yaml
Type: System.UInt32[]
Parameter Sets: SessionIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификатор экземпляра удаляемого сеанса CIM. **InstanceId** — это глобальный уникальный идентификатор (GUID), который однозначно определяет сеанс CIM. Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.

**InstanceId** хранится в свойстве **InstanceId** объекта, представляющего сеанс CIM.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает понятное имя удаляемого сеанса CIM. С этим параметром можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Нет

Этот командлет не принимает входные объекты.

## Выходные данные

### System.Object

Этот командлет возвращает объект, содержащий сведения о сеансе CIM.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)
