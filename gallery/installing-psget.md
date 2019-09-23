---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Установка PowerShellGet
ms.openlocfilehash: a0ef46a9ee4bbf668a58067256d098967bde48c5
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71143597"
---
# <a name="installing-powershellget"></a>Установка PowerShellGet

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>Модуль PowerShellGet входит в комплект поставки в следующих выпусках:

- [Windows 10](https://www.microsoft.com/windows) или более поздняя версия;
- [Windows Server 2016](/windows-server/windows-server) или более поздняя версия;
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) или более поздняя версия;
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases).

## <a name="get-the-latest-version-from-powershell-gallery"></a>Получение последней версии из коллекции PowerShell

Перед обновлением **PowerShellGet** всегда устанавливайте последний поставщик **NuGet**. Откройте сеанс PowerShell с повышенными привилегиями и выполните следующую команду.

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>Для систем с PowerShell 5.0 (или более поздней версии) можно установить последнюю версию PowerShellGet

Чтобы установить PowerShellGet в Windows 10, Windows Server 2016, а также любой системе с WMF 5.0, 5.1 или PowerShell 6, выполните следующие команды из сеанса PowerShell с повышенными привилегиями.

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

`Update-Module` позволяет получить более новые версии.

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-preview"></a>Для систем под управлением PowerShell 3 или PowerShell 4, на которых установлена предварительная версия PackageManagement

1. В сеансе PowerShell с повышенными привилегиями используйте `Save-Module`, чтобы сохранить модули в локальном каталоге.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder
   Exit
   ```

1. Убедитесь, что модули **PowerShellGet** и **PackageManagement** не загружаются в других процессах.
1. Удалите содержимое папок `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` и `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.
1. Снова откройте консоль PowerShell с повышенными привилегиями, а затем выполните следующие команды.

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```
