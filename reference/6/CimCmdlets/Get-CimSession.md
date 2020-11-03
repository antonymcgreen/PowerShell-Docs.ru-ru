---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: c40367d0458c3670b9d684cd0c3b4b2a3631b3e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228245"
---
# Get-CimSession

## Краткий обзор
Возвращает объекты сеанса CIM из текущего сеанса.

## SYNTAX

### Компутернамесет (по умолчанию)

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### SessionId

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### инстанцеидсет

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### Имя

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## DESCRIPTION

По умолчанию командлет получает все сеансы CIM, созданные в текущем сеансе PowerShell. `Get-CimSession`Для получения сеансов, предназначенных для конкретных компьютеров, можно использовать параметры, или можно указать сеансы по их именам или другим идентификаторам. `Get-CimSession` не получает сеансы CIM, созданные в других сеансах PowerShell или созданные на других компьютерах.

Дополнительные сведения о сеансах CIM см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

## Примеры

### Пример 1. получение сеансов CIM из текущего сеанса PowerShell

Этот пример создает сеансы CIM с помощью [New-CimSession](New-CimSession.md), а затем получает сеансы CIM с помощью `Get-CimSession` .

```powershell
New-CimSession -ComputerName Server01,Server02
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Пример 2. получение сеансов CIM для определенного компьютера

В этом примере возвращаются сеансы CIM, подключенные к компьютеру с именем **Server02** .

```powershell
Get-CimSession -ComputerName Server02
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Пример 3. Получение списка сеансов CIM и последующее форматирование списка

Этот пример получает все сеансы CIM в текущем сеансе PowerShell и отображает таблицу, содержащую только свойства **ComputerName** и **InstanceId** .

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### Пример 4. получение всех сеансов CIM с конкретными именами

В этом примере получаются все сеансы CIM, имена которых начинаются с **серв** .

```powershell
Get-CimSession -ComputerName Serv*
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Пример 5. получение конкретного сеанса CIM

В этом примере возвращается сеанс CIM с **идентификатором** 2.

```powershell
Get-CimSession -ID 2
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

## PARAMETERS

### -ComputerName

Указывает имя компьютера, к которому подключены сеансы CIM. Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Id

Указывает идентификатор получаемого сеанса CIM. Для нескольких идентификаторов используйте запятые для разделения идентификаторов или используйте оператор Range ( `..` ), чтобы указать диапазон идентификаторов. **Идентификатор** — это целое число, которое однозначно определяет сеанс CIM в текущем сеансе PowerShell.

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

Указывает идентификаторы экземпляров получаемого сеанса CIM.

**InstanceId** — это глобальный уникальный идентификатор (GUID), который однозначно определяет сеанс CIM. Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.

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

Возвращает один или несколько сеансов CIM, которые содержат указанные понятные имена. Можно использовать подстановочные знаки.

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

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

## Выходные данные

### Microsoft.Management.Infrastructure.CimSession

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Format-Table](../microsoft.powershell.utility/format-table.md)

[New-CimSession](New-CimSession.md)

[Remove-CimSession](remove-cimsession.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)
