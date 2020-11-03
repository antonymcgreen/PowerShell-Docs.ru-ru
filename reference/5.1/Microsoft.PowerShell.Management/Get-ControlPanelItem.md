---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228402"
---
# Get-ControlPanelItem

## Краткий обзор
Получает элементы панели управления.

## SYNTAX

### Регуларнаме (по умолчанию)

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### каноникалнаме

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ControlPanelItem`Командлет возвращает элементы панели управления на локальном компьютере. С его помощью можно находить элементы панели управления по имени, категории или описанию даже в системах, в которых нет пользовательского интерфейса.

Этот командлет возвращает только элементы панели управления, которые могут быть открыты в системе. На компьютерах, на которых нет панели управления или проводника, этот командлет получает только элементы панели управления, которые могут открываться без этих компонентов.

Этот командлет впервые появился в Windows PowerShell 3.0. Он работает только в Windows 8 и Windows Server 2012 и более поздних версиях.

## Примеры

### Пример 1. получение всех элементов панели управления

Эта команда возвращает все элементы панели управления на локальном компьютере.

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### Пример 2. Получение элементов панели управления по имени

Этот пример возвращает элементы панели управления, в именах которых есть программа или приложение.

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### Пример 3. Получение элементов панели управления по категориям

Эта команда возвращает все элементы панели управления в категориях, в именах которых есть безопасность.

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### Пример 4. Открытие элемента панели управления

В этом примере открывается элемент панели управления Брандмауэр Windows на локальном компьютере.

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem`Командлет возвращает элемент панели управления. `Show-ControlPanelItem`Командлет откроет его.

### Пример 5. Получение элементов панели управления на удаленном компьютере

В этом примере возвращается элемент панели управления шифрование диска BitLocker на удаленном компьютере Server01.
`Invoke-Command`Командлет запускает `Get-ControlPanelItem` командлет удаленно.

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### Пример 6. Поиск в описаниях элементов панели управления

В этом примере выполняется поиск в свойстве **Description** элементов панели управления, чтобы получить только те, которые содержат имя **устройства** .

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

`Get-ControlPanelItem`Командлет возвращает все элементы панели управления. `Where-Object`Командлет фильтрует элементы по значению свойства **Description** .

## PARAMETERS

### -Каноникалнаме

Указывает в виде массива строк элементы панели управления по каноническому имени или шаблонам имен, которые получает этот командлет. Разрешено использовать подстановочные знаки. При вводе нескольких имен этот командлет получает элементы панели управления, соответствующие любому из имен, как будто элементы в списке имен были разделены оператором "или".

По умолчанию этот командлет получает все элементы панели управления в системе.

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

### -Category

Указывает в виде массива строк категории элементов панели управления в указанных категориях, которые получает этот командлет. Введите имя категории или шаблон имени. Разрешено использовать подстановочные знаки. При вводе нескольких имен этот командлет получает элементы панели управления, соответствующие любому из имен, как будто элементы в списке имен были разделены оператором "или". По умолчанию этот командлет получает все элементы панели управления в системе.

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

### -Name

Указывает в виде массива строк имена или шаблоны имен или имен элементов панели управления, которые получает этот командлет.
Разрешено использовать подстановочные знаки. В этот командлет можно также передать по конвейеру имя или шаблон имени.

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру имя или шаблон имени.

## Выходные данные

### Microsoft. PowerShell. Commands. ControlPanelItem

Этот командлет возвращает элементы панели управления на локальном компьютере.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Show-ControlPanelItem](Show-ControlPanelItem.md)
