---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 66a6bfeda557894e224753018ff9087de9887cc7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892862"
---
# Get-PackageProvider

## Краткий обзор
Возвращает список поставщиков пакетов, подключенных к системе управления пакетами.

## SYNTAX

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-PackageProvider** возвращает список поставщиков пакетов, подключенных к системе управления пакетами.
К ним относятся, например, PSModule, NuGet и Chocolatey.
Результаты можно отфильтровать на основе имен (полных или их части) поставщиков.

## Примеры

### Пример 1. Получение всех загруженных в настоящее время поставщиков пакетов

```
PS C:\> Get-PackageProvider
```

Эта команда возвращает список всех поставщиков пакетов, загруженных в настоящий момент на локальный компьютер.

### Пример 2. Получение списка всех доступных поставщиков пакетов

```
PS C:\> Get-PackageProvider -ListAvailable
```

Эта команда возвращает список всех поставщиков пакетов, доступных на локальном компьютере.

### Пример 3. Динамическое получение поставщика пакетов

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

Эта команда автоматически устанавливает поставщик Chocolatey, если он еще не установлен на компьютере.

## PARAMETERS

### -Force
Указывает, что этот командлет принудительно выполняет все доступные для этого командлета действия.
Это означает, что в командлете **Get-PackageProvider** параметр *Force* действует так же, как и параметр *ForceBootstrap*.

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

### -ForceBootstrap
Указывает, что этот командлет заставляет систему управления пакетами автоматически установить поставщик пакетов.

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

### -ListAvailable
Получает все установленные поставщики.
**Get-PackageProvider** Получает поставщик в путях, указанных в переменной среды **PSModulePath** , а также в папках сборки поставщика пакетов:

**$env:P Рограмфилес\паккажеманажемент\провидерассемблиес * * * * $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies**

Без этого параметра командлет **Get-PackageProvider** получает только поставщики, загруженные в текущем сеансе.

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

### -Name
Задает одно или несколько имен поставщиков или их часть.
Имена нескольких поставщиков нужно разделять запятыми.
Допустимые значения: имена установленных поставщиков пакетов, поставки PackageManagement с набором поставщиков по умолчанию, в том числе поставщики **PSModule** и **MSI**.

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

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### PackageProvider[]

## ПРИМЕЧАНИЯ

> [!IMPORTANT]
> По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1. Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка. Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.

## Связанные ссылки

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Unregister-PackageSource](Unregister-PackageSource.md)
