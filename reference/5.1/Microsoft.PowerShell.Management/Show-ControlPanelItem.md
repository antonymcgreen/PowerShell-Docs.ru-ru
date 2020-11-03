---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227866"
---
# Show-ControlPanelItem

## Краткий обзор
Открывает элементы панели управления.

## SYNTAX

### Регуларнаме (по умолчанию)

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### каноникалнаме

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### ControlPanelItem

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## DESCRIPTION

`Show-ControlPanelItem`Командлет открывает элементы панели управления на локальном компьютере. Его можно использовать для открытия элементов панели управления по имени, категории или описанию даже в системах без пользовательского интерфейса. Элементы панели управления можно передать из `Get-ControlPanelItem` командлета в `Show-ControlPanelItem` .

`Show-ControlPanelItem` выполняет поиск только элементов панели управления, которые могут быть открыты в системе. На компьютерах, на которых не установлена **Панель управления** или **проводник** , `Show-ControlPanelItem` выполняет поиск только элементов панели управления, которые могут открываться без этих компонентов.

Этот командлет появился в Windows PowerShell 3,0 и работает в Windows 8, Windows Server 2012 и более поздних версиях.

## Примеры

### Пример 1. Отображение элемента панели управления

В этом примере запускается элемент панели управления **Автозапуск** .

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### Пример 2. Передача элемента панели управления по конвейеру в этот командлет

В этом примере открывается элемент панели управления **брандмауэром защитника Windows** на локальном компьютере.
Имя элемента панели управления брандмауэра Windows изменилось по сравнению с версиями Windows. В этом примере для поиска элемента панели управления используется шаблон с подстановочными знаками.

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem` Возвращает элемент панели управления, и `Show-ControlPanelItem` командлет открывает его.

### Пример 3. Использование имени файла для открытия элемента панели управления

В этом примере элемент панели управления **программы и компоненты** открывается с использованием имени приложения.

```powershell
appwiz.cpl
```

Этот метод является альтернативой использованию `Show-ControlPanelItem` команды.

> [!NOTE]
> В PowerShell можно опустить расширение файла. cpl для файлов панели управления, так как оно включается в значение `$env:PathExt` переменной среды.

## PARAMETERS

### -Каноникалнаме

Задает элементы панели управления с использованием указанных канонических имен или шаблонов имен. Можно использовать подстановочные знаки. При вводе нескольких имен этот командлет открывает элементы панели управления, соответствующие любому из имен, как если бы элементы списка имен были разделены оператором **или** .

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Указывает элементы панели управления, открываемые при отправке объектов элементов панели управления. Введите переменную, содержащую объекты элементов панели управления, или введите команду или выражение, которое получает объекты элементов панели управления, такие как `Get-ControlPanelItem` .

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имена элементов панели управления. Можно использовать подстановочные знаки. При вводе нескольких имен этот командлет открывает элементы панели управления, соответствующие любому из имен, как если бы элементы списка имен были разделены оператором **или** .

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. String, Microsoft. PowerShell. Commands. ControlPanelItem

К этому командлету можно передать объект имени или элемента панели управления.

## Выходные данные

### Нет

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-ControlPanelItem](Get-ControlPanelItem.md)
