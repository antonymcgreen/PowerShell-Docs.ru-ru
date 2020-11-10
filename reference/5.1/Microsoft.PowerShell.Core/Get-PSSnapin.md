---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 156cadecd87910e3c3312e84929b16709770641d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388677"
---
# Get-PSSnapin

## Краткий обзор
Получает оснастки Windows PowerShell на компьютере.

## SYNTAX

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## DESCRIPTION

`Get-PSSnapin`Командлет возвращает оснастки Windows PowerShell, которые были добавлены в текущий сеанс или которые были зарегистрированы в системе. Этот командлет перечисляет оснастки в том порядке, в котором они обнаружены.

`Get-PSSnapin` Возвращает только зарегистрированные оснастки. Чтобы зарегистрировать оснастку Windows PowerShell, используйте средство InstallUtil, входящее в состав Microsoft .NET Framework 2,0. Дополнительные сведения см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).

Начиная с Windows PowerShell 3,0, основные команды, входящие в Windows PowerShell, упаковываются в модули. Исключение составляет **Microsoft.PowerShell.Core** , который является оснасткой (PSSnapin).
По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core**. Модули импортируются автоматически при первом использовании `Import-Module` . для их импорта можно использовать командлет.

## Примеры

### Пример 1. получение оснасток, загруженных в данный момент

```
PS C:\> Get-PSSnapIn
```

Эта команда возвращает оснастки Windows PowerShell, загруженные в сеанс на текущий момент. Сюда входят как оснастки, установленные вместе с Windows PowerShell, так и оснастки, добавленные в сеанс.

### Пример 2. получение зарегистрированных оснасток

```
PS C:\> get-PSSnapIn -Registered
```

Эта команда получает оснастки Windows PowerShell, зарегистрированные на компьютере, включая оснастки, уже добавленные в сеанс. В выходные данные не включаются оснастки, установленные вместе с Windows PowerShell или библиотеками динамической компоновки (библиотеками DLL) оснасток Windows PowerShell, которые еще не зарегистрированы в системе.

### Пример 3. Получение текущих оснасток, соответствующих строке

```
PS C:\> Get-PSSnapIn -Name smp*
```

Эта команда получает оснастки Windows PowerShell в текущем сеансе, имена которых начинаются с SMP.

## PARAMETERS

### -Name

Указывает массив имен оснасток. Этот командлет возвращает только указанные оснастки Windows PowerShell. Допускаются подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Зарегистрировано

Указывает, что этот командлет получает оснастки Windows PowerShell, которые были зарегистрированы в системе, даже если они еще не были добавлены в сеанс.

Оснастки, устанавливаемые с Windows PowerShell, не включаются в этот список.

Без этого параметра `Get-PSSnapin` получает оснастки Windows PowerShell, которые были добавлены в сеанс.

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

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. PSSnapInInfo

`Get-PSSnapin` Возвращает объект для каждой оснастки, которую он получает.

## ПРИМЕЧАНИЯ

Начиная с Windows PowerShell 3,0, основные команды, устанавливаемые вместе с Windows PowerShell, упаковываются в модули. В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях Windows PowerShell, основные команды упаковываются в оснастки ( **PSSnapin** ). Исключением является **Microsoft. PowerShell. Core** , который всегда является оснасткой. Кроме того, удаленные сеансы, такие как запущенные `New-PSSession` командлетом, являются сеансами предыдущих версий, включающими основные оснастки.

 Дополнительные сведения о методе **CreateDefault2** , который создает сеансы нового стиля с основными модулями, см. в разделе [метод CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).

## Связанные ссылки

[Add-PSSnapin](Add-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
