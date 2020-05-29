---
ms.date: 09/19/2019
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Установка PowerShellGet
ms.openlocfilehash: f42eb0df101eb63a5dc267196fa9f666747b8e35
ms.sourcegitcommit: 23ea4a36ee85f923684657de5313a5adf0b6b094
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83727801"
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

### <a name="for-computers-running-powershell-30-or-powershell-40"></a>Для компьютеров с PowerShell 3.0 или 4.0

Эти инструкции применимы к компьютерам, на которых установлена предварительная версия **PackageManagement** или не установлены никакие версии **PowerShellGet**.

Командлет `Save-Module` используется в обоих наборах инструкций. `Save-Module` скачивает и сохраняет модуль и все зависимости из зарегистрированного репозитория. Самая последняя версия модуля сохраняется по указанному пути на локальном компьютере, но не устанавливается. Чтобы установить модули в PowerShell 3.0 или 4.0, скопируйте сохраненные папки модуля в `$env:ProgramFiles\WindowsPowerShell\Modules`.

Дополнительные сведения см. в статье [Save-Module](/powershell/module/PowershellGet/Save-Module).

> [!NOTE]
> PowerShell 3.0 и 4.0 поддерживают только одну версию модуля. Начиная с версии PowerShell 5.0 модули устанавливаются в папку `<modulename>\<version>`. Это позволяет устанавливать несколько версий параллельно. Скачав модуль с помощью `Save-Module`, необходимо скопировать файлы из `<modulename>\<version>` в папку `<modulename>` на целевом компьютере.

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>Компьютеры с установленной предварительной версией PackageManagement

1. В сеансе PowerShell используйте `Save-Module`, чтобы сохранить модули в локальном каталоге.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Убедитесь, что модули **PowerShellGet** и **PackageManagement** не загружаются в других процессах.
1. Удалите содержимое папок `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` и `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.
1. Снова откройте консоль PowerShell с повышенными привилегиями, а затем выполните следующие команды.

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a>Компьютеры без PowerShellGet

Если на компьютере нет какой-либо версии **PowerShellGet**, для скачивания модулей необходим компьютер с **PowerShellGet**.

1. На компьютере с установленным **PowerShellGet** используйте `Save-Module`, чтобы скачать текущую версию **PowerShellGet**. Скачиваются две папки: **PowerShellGet** и **PackageManagement**. Каждая папка содержит вложенную папку с номером версии.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Скопируйте папки **PowerShellGet** и **PackageManagement** на компьютер, на котором не установлен **PowerShellGet**.

   Каталог назначения: `$env:ProgramFiles\WindowsPowerShell\Modules`.
