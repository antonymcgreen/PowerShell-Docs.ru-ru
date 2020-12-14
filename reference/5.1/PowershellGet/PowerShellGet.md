---
Download Help Link: https://go.microsoft.com/fwlink/?LinkId=393271
Help Version: 5.2.0.0
keywords: powershell,командлет
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 130582b1b9f18a8f6ada7c009c6d25a7dab75e46
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890718"
---
# Модуль PowerShellGet

## Описание

PowerShellGet — это модуль с командами для обнаружения, установки, обновления и публикации артефактов PowerShell, таких как модули, ресурсы DSC, возможности ролей и сценарии.

> [!IMPORTANT]
> По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1. Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка. Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.

## Командлеты модуля PowerShellGet

### [Find-Command](Find-Command.md)
Ищет команды PowerShell в модулях.

### [Find-DscResource](Find-DscResource.md)
Находит ресурс DSC.

### [Find-Module](Find-Module.md)
Находит модули в репозитории, соответствующие указанным критериям.

### [Find-RoleCapability](Find-RoleCapability.md)
Находит возможности ролей в модулях.

### [Find-Script](Find-Script.md)
Поиск скрипта.

### [Get-InstalledModule](Get-InstalledModule.md)
Возвращает список модулей на компьютере, которые были установлены с помощью PowerShellGet.

### [Get-InstalledScript](Get-InstalledScript.md)
Возвращает установленный скрипт.

### [Get-PSRepository](Get-PSRepository.md)
Возвращает репозитории PowerShell.

### [Install-Module](Install-Module.md)
Скачивает один или несколько модулей из репозитория и устанавливает их на локальный компьютер.

### [Install-Script](Install-Script.md)
Устанавливает скрипт.

### [New-ScriptFileInfo](New-ScriptFileInfo.md)
Создание файла сценария с метаданными.

### [Publish-Module](Publish-Module.md)
Публикует указанный модуль с локального компьютера в коллекцию в Интернете.

### [Publish-Script](Publish-Script.md)
Публикует скрипт.

### [Register-PSRepository](Register-PSRepository.md)
Регистрирует репозиторий PowerShell.

### [Save-Module](Save-Module.md)
Сохраняет модуль и его зависимости на локальном компьютере, но не устанавливает модуль.

### [Save-Script](Save-Script.md)
Сохраняет скрипт.

### [Set-PSRepository](Set-PSRepository.md)
Задает значения для зарегистрированного репозитория.

### [Test-ScriptFileInfo](Test-ScriptFileInfo.md)
Проверяет блок комментариев для скрипта.

### [Uninstall-Module](Uninstall-Module.md)
Удаляет модуль.

### [Uninstall-Script](Uninstall-Script.md)
Удаляет скрипт.

### [Unregister-PSRepository](Unregister-PSRepository.md)
Отмена регистрации репозитория.

### [Update-Module](Update-Module.md)
Скачивает последние версии указанных модулей из веб-коллекции и устанавливает их на локальном компьютере.

### [Update-ModuleManifest](Update-ModuleManifest.md)
Обновляет файл манифеста модуля.

### [Update-Script](Update-Script.md)
Обновляет скрипт.

### [Update-ScriptFileInfo](Update-ScriptFileInfo.md)
Обновляет сведения для скрипта.
