---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: d710881f4444a35bd1dca7950292660889a3e38c
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "93230157"
---
# Get-DscResource

## Краткий обзор
Получает ресурсы настройки требуемого состояния (DSC), которые имеются на компьютере.

## SYNTAX

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## DESCRIPTION

`Get-DscResource`Командлет извлекает ресурсы DSC PowerShell, имеющиеся на компьютере. Этот командлет обнаруживает только ресурсы, установленные в PSModulePath. В нем отображаются сведения о встроенных и пользовательских поставщиках, создаваемых пользователем. Этот командлет также отображает сведения о составных ресурсах, которые являются другими конфигурациями, упакованными в модуль или созданными во время выполнения в сеансе.

## Примеры

### Пример 1. получение всех ресурсов на локальном компьютере

```powershell
 Get-DscResource
```

Эта команда возвращает все ресурсы на локальном компьютере.

### Пример 2. Получение ресурса путем указания имени

```powershell
Get-DscResource -Name "WindowsFeature"
```

Эта команда возвращает ресурс WindowsFeature.

### Пример 3. получение всех ресурсов из модуля

```powershell
Get-DscResource -Module "xHyper-V"
```

Эта команда получает все ресурсы из модуля Ксхипер-V.

### Пример 4. Получение ресурса с помощью подстановочных знаков

```powershell
Get-DscResource -Name P*,r*
```

Эта команда возвращает все ресурсы, соответствующие шаблону с подстановочным знаком, заданному параметром **Name** .

### Пример 5. получение синтаксиса ресурсов

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

Эта команда возвращает ресурс WindowsFeature и отображает синтаксис для ресурса.

### Пример 6. получение всех свойств ресурса

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

Эта команда возвращает  ресурс пользователя, а затем использует оператор конвейера для возврата всех свойств для ресурса пользователя.

### Пример 7. получение всех ресурсов из указанного модуля с указанной версией

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

Эта команда получает все ресурсы из модуля Ксхипер-V с версией 3.0.0.0.

## PARAMETERS

### -Module

Указывает имя или полное имя модуля, для которого необходимо просмотреть ресурс DSC.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Указывает массив имен ресурса DSC для просмотра.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Syntax

Указывает, что командлет возвращает представление синтаксиса для указанных ресурсов DSC. Возвращаемый синтаксис показывает, как использовать ресурсы в скрипте PowerShell.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String[]

### System.Object

## Выходные данные

### Microsoft. PowerShell. Десиредстатеконфигуратион. Дскресаурцеинфо []

### string[]

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Общие сведения о настройке требуемого состояния PowerShell](/powershell/scripting/dsc/overview/overview)

[Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
