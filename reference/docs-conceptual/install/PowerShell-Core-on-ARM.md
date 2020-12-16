---
title: Установка PowerShell Core в ARM
description: Установка PowerShell Core в системах на основе ARM
ms.date: 11/11/2020
ms.openlocfilehash: 85a2cccb18341ffee8c81430bc8490e5d3e97b41
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892078"
---
# <a name="powershell-core-on-arm"></a>PowerShell Core для ARM

Поддержка PowerShell в системах ARM основана на **политиках жизненного цикла ОС, поддерживаемых .NET Core**.

Версия PowerShell 7.1 основана на [политике жизненного цикла ОС, поддерживаемой .NET Core 3.1,](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) и поддерживает следующие платформы:

|         Операционная система          |          Version           | Архитектуры |          Жизненный цикл           |
| ------------------- | -------------------------- | ------------- | ---------------------------- |
| Windows Nano Server | Версия 1803+              | ARM32         | [Windows][Windows-lifecycle] |
| Alpine Linux        | 3.10+                      | ARM64         | [Alpine][Alpine-lifecycle]   |
| Debian              | 9+                         | ARM32, ARM64  | [Debian][Debian-lifecycle]   |
| Ubuntu              | 20.10, 20.04, 18.04, 16.04 | ARM32, ARM64  | [Ubuntu][Ubuntu-lifecycle]   |

Версия PowerShell 7.0 основана на [политике жизненного цикла ОС, поддерживаемой .NET Core 5.0,](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) и поддерживает следующие платформы:

|        Операционная система         |          Version           | Архитектуры |          Жизненный цикл           |
| ----------------- | -------------------------- | ------------- | ---------------------------- |
| Клиент Windows 10 | Версия 1607+              | ARM64         | [Windows][Windows-lifecycle] |
| Alpine Linux      | 3.11 и выше                      | ARM64         | [Alpine][Alpine-lifecycle]   |
| Debian            | 9+                         | ARM32, ARM64  | [Debian][Debian-lifecycle]   |
| Ubuntu            | 20.10, 20.04, 18.04, 16.04 | ARM32, ARM64  | [Ubuntu][Ubuntu-lifecycle]   |

[Windows-lifecycle]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[Alpine-lifecycle]: https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases
[Debian-lifecycle]: https://wiki.debian.org/DebianReleases
[Ubuntu-lifecycle]: https://wiki.ubuntu.com/Releases

Инструкции по установке см. в следующих статьях:

- [Windows 10 на архитектуре ARM](installing-powershell-core-on-windows.md#installing-the-zip-package)
- [Windows 10 IoT Корпоративная](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-enterprise)
- [Windows 10 IoT Базовая](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-core)
- [Raspbian](installing-powershell-core-on-linux.md#raspbian)
