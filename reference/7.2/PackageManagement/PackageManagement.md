---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 86e6f37f6f7f0527c5dcca309cf581cb6f1b4de5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599994"
---
# Модуль PackageManagement

## Описание

В этом разделе отображаются разделы справки по командлетам Управление пакетами.

> [!IMPORTANT]
> Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1. Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка. Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.

## Командлеты PackageManagement

### [Find-Package](Find-Package.md)
Находит пакеты программного обеспечения в доступных источниках пакетов.

### [Find-PackageProvider](Find-PackageProvider.md)
Возвращает список поставщиков пакетов Управление пакетами, доступных для установки.

### [Get-Package](Get-Package.md)
Возвращает список всех пакетов программного обеспечения, установленных с помощью **PackageManagement**.

### [Get-PackageProvider](Get-PackageProvider.md)
Возвращает список поставщиков пакетов, подключенных к системе управления пакетами.

### [Get-PackageSource](Get-PackageSource.md)
Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.

### [Import-PackageProvider](Import-PackageProvider.md)
Добавляет поставщики пакетов Управление пакетами в текущий сеанс.

### [Install-Package](Install-Package.md)
Устанавливает один или несколько пакетов программного обеспечения.

### [Install-PackageProvider](Install-PackageProvider.md)
Устанавливает один или несколько поставщиков пакетов Управление пакетами.

### [Register-PackageSource](Register-PackageSource.md)
Добавляет источник пакета для указанного поставщика пакетов.

### [Save-Package](Save-Package.md)
Сохраняет пакеты на локальном компьютере, не устанавливая их.

### [Set-PackageSource](Set-PackageSource.md)
Заменяет источник пакета для указанного поставщика пакетов.

### [Uninstall-Package](Uninstall-Package.md)
Удаляет один или несколько пакетов программного обеспечения.

### [Unregister-PackageSource](Unregister-PackageSource.md)
Удаляет зарегистрированный источник пакета.
