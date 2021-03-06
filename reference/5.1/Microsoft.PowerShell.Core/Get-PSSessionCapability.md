---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: d76baaef31c27184bc355b6f0fc79ca67b986157
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226673"
---
# Get-PSSessionCapability

## Краткий обзор
Возвращает возможности конкретного пользователя в конфигурации ограниченного сеанса.

## SYNTAX

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-PSSessionCapability** Возвращает возможности конкретного пользователя в конфигурации с ограниченным сеансом.
Используйте этот командлет для аудита настроенных конфигураций сеансов для пользователей.

Начиная с Windows PowerShell 5,0, можно использовать свойство **RoleDefinitions** в файле конфигурации сеанса (. pssc).
Использование этого свойства позволяет предоставлять пользователям различные возможности для одной ограниченной конечной точки на основе членства в группе.
Командлет **Get-PSSessionCapability** сокращает сложность при аудите этих конечных точек, позволяя определить точные возможности, предоставленные пользователю.

По умолчанию командлет **Get-PSSessionCapability** возвращает список команд, которые указанный пользователь может запускать в указанной конечной точке.
Это эквивалентно пользователю, выполняющему **команду Get-Command** в указанной конечной точке.
При запуске с параметром *Full* этот командлет возвращает объект **InitialSessionState** .
Этот объект содержит сведения о пространстве выполнения Windows PowerShell, с которым будет взаимодействовать указанный пользователь для указанной конечной точки.
Он содержит такие сведения, как языковой режим, политика выполнения и переменные среды.

## Примеры

### Пример 1. получение команд, доступных пользователю

```
PS C:\> Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

В этом примере возвращаются команды, доступные пользователю, Контосо\усер при подключении к ограниченной конечной точке Endpoint1 на локальном компьютере.

### Пример 2. Получение сведений о пространстве выполнения для пользователя

```
PS C:\> Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

В этом примере возвращаются сведения о пространстве выполнения, с которым будет взаимодействовать пользователь, Контосо\усер при подключении к ограниченной конечной точке Endpoint1.

## PARAMETERS

### -ConfigurationName
Задает проверяемую конфигурацию ограниченного сеанса (конечную точку).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full
Указывает, что этот командлет возвращает все начальное состояние сеанса для указанного пользователя в заданной ограниченной конечной точке.

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

### -Username
Указывает пользователя, возможности которого проверяются.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### System.Management.Automation.AliasInfo

### System.Management.Automation.FunctionInfo

### System.Management.Automation.Runspaces.IniТиалсессионстате

## ПРИМЕЧАНИЯ

## Связанные ссылки

[New-PSRoleCapabilityFile](New-PSRoleCapabilityFile.md)
