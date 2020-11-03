---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
online version: ''
schema: 2.0.0
ms.openlocfilehash: 34998e7c4a6876821df949019970dc1d87297397
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232929"
---
# Get-PSSubsystem

## Краткий обзор
Извлекает сведения о подсистемах, зарегистрированных в PowerShell.

## SYNTAX

### Жеталлсет (по умолчанию)

```
Get-PSSubsystem [<CommonParameters>]
```

### жетбикиндсет

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### жетбитипесет

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## DESCRIPTION

Извлекает сведения о подсистемах, зарегистрированных в PowerShell.

> [!NOTE]
> Это экспериментальная функция. Этот командлет доступен только при `PSSubsystemPluginModel` включенной функции. Дополнительные сведения см. [в разделе Использование экспериментальных функций](/powershell/scripting/learn/experimental-features).

Эта функция позволяет разделять компоненты `System.Management.Automation.dll` в отдельные подсистемы, находящиеся в их собственной сборке. Такое разделение сокращает объем дискового пространства ядра PowerShell и позволяет этим компонентам стать необязательными для минимальной установки PowerShell.

В настоящее время поддерживается только подсистема **CommandPredictor** . Эта подсистема используется вместе с модулем PSReadLine для предоставления настраиваемых подключаемых модулей прогнозирования. В будущем **задание** , **CommandCompleter** , **удаленное взаимодействие** и другие компоненты можно будет разделить на сборки подсистемы за пределами `System.Management.Automation.dll`.

## Примеры

### Пример 1. Отображение всех доступных подсистем

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### Пример 2. Отображение всех доступных подсистем определенного типа

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## PARAMETERS

### -Kind


Указывает тип возвращаемой подсистемы. Допустимые значения: `CommandPredictor` .

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Субсистемтипе

Указывает тип возвращаемой подсистемы.

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. подсистема. Субсистемкинд

### System.Type

## Выходные данные

### System. Management. Automation. подсистема. Субсистеминфо

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_experimental_features](about/about_experimental_features.md)

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Get-ExperimentalFeature.md)

[Get-ExperimentalFeature](Get-ExperimentalFeature.md)

[Использование экспериментальных возможностей](/powershell/scripting/learn/experimental-features)
