---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 472a4c8fbb9eb0d37827aff4fcfd6bb9a67f4743
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226665"
---
# Get-PSSnapin

## Краткий обзор
Получает оснастки Windows PowerShell на компьютере.

## SYNTAX

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-PSSnapin** получает оснастки Windows PowerShell, которые были добавлены в текущий сеанс или которые были зарегистрированы в системе.
Этот командлет перечисляет оснастки в том порядке, в котором они обнаружены.

**Get-PSSnapin** получает только зарегистрированные оснастки. Чтобы зарегистрировать оснастку Windows PowerShell, используйте средство InstallUtil, входящее в состав Microsoft .NET Framework 2,0.
Дополнительные сведения см. в разделе [Регистрация командлетов, поставщиков и ведущих приложений](https://go.microsoft.com/fwlink/?LinkID=143619) в библиотеке MSDN.

Начиная с Windows PowerShell 3,0, основные команды, входящие в Windows PowerShell, упаковываются в модули.
Исключение составляет **Microsoft.PowerShell.Core** , который является оснасткой (PSSnapin).
По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core**.
Модули импортируются автоматически при первом использовании. для их импорта можно использовать командлет Import-Module.

## Примеры

### Пример 1. получение оснасток, загруженных в данный момент

```
PS C:\> Get-PSSnapIn
```

Эта команда возвращает оснастки Windows PowerShell, загруженные в сеанс на текущий момент.
Сюда входят как оснастки, установленные вместе с Windows PowerShell, так и оснастки, добавленные в сеанс.

### Пример 2. получение зарегистрированных оснасток

```
PS C:\> get-PSSnapIn -Registered
```

Эта команда получает оснастки Windows PowerShell, зарегистрированные на компьютере, включая оснастки, уже добавленные в сеанс.
В выходные данные не включаются оснастки, установленные вместе с Windows PowerShell или библиотеками динамической компоновки (библиотеками DLL) оснасток Windows PowerShell, которые еще не зарегистрированы в системе.

### Пример 3. Получение текущих оснасток, соответствующих строке

```
PS C:\> Get-PSSnapIn -Name smp*
```

Эта команда получает оснастки Windows PowerShell в текущем сеансе, имена которых начинаются с SMP.

## PARAMETERS

### -Name
Указывает массив имен оснасток.
Этот командлет возвращает только указанные оснастки Windows PowerShell. Допускаются подстановочные знаки.

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

Без этого параметра командлет **Get-PSSnapin** получает оснастки Windows PowerShell, которые были добавлены в сеанс.

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
Командлет Get-PSSnapin возвращает объект для каждой получаемой оснастки.

## ПРИМЕЧАНИЯ

* Начиная с Windows PowerShell 3,0, основные команды, устанавливаемые вместе с Windows PowerShell, упаковываются в модули. В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях Windows PowerShell, основные команды упаковываются в оснастки ( **PSSnapin** ). Исключением является **Microsoft. PowerShell. Core** , который всегда является оснасткой. Кроме того, удаленные сеансы, например, запущенные командлетом New-PSSession, являются сеансами предыдущих версий, включающими основные оснастки.

  Дополнительные сведения о методе **CreateDefault2** , который создает сеансы более новых версий с основными модулями, см. в разделе [метод CREATEDEFAULT2](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) в библиотеке MSDN.

## Связанные ссылки

[Add-PSSnapin](Add-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
