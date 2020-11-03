---
description: Список командлетов, предназначенных для использования с поставщиками PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 3391dce21cec5080020640be75e4c4df9da0c812
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232457"
---
# <a name="about-core-commands"></a>Основные команды

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Список командлетов, предназначенных для использования с поставщиками PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

PowerShell включает набор командлетов, специально предназначенных для управления элементами в хранилищах данных, предоставляемых поставщиками Windows PowerShell.
Эти командлеты можно использовать для управления всеми типами данных, которые поставщики делают доступными. Для получения дополнительных сведений о поставщиках введите «Get-Help about_providers».

Например, с помощью командлета Get-ChildItem можно вывести список файлов в каталоге файловой системы, ключи в разделе реестра или элементы, предоставляемые поставщиком, который вы создаете или скачиваете.

Ниже приведен список командлетов PowerShell, предназначенных для использования с поставщиками.

Командлеты ChildItem

- Get-ChildItem

Командлеты содержимого

- Add-Content
- Clear-Content
- Get-Content
- Set-Content

Командлеты элементов

- Clear-Item
- Copy-Item
- Get-Item
- Invoke-Item
- Move-Item
- New-Item
- Remove-Item
- Rename-Item
- Set-Item

Командлеты ItemProperty

- Clear-ItemProperty
- Copy-ItemProperty
- Get-ItemProperty
- Move-ItemProperty
- New-ItemProperty
- Remove-ItemProperty
- Rename-ItemProperty
- Set-ItemProperty

Командлеты Location

- Get-Location
- Pop-Location
- Push-Location
- Set-Location

Командлеты пути

- Join-Path
- Convert-Path
- Split-Path
- Resolve-Path
- Test-Path

Командлеты PSDrive

- Get-PSDrive
- New-PSDrive
- Remove-PSDrive

Командлеты PSProvider

- Get-PSProvider

Для получения дополнительных сведений о командлете введите `get-help <cmdlet-name>` .

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Providers](about_Providers.md)
