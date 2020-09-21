---
ms.date: 09/19/2019
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Установка PowerShellGet
ms.openlocfilehash: 4a10699be9ff2b64e5848c6749bdd3dedf55e3c7
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162517"
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
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>Для систем с PowerShell 5.0 (или более поздней версии) можно установить последнюю версию PowerShellGet

Чтобы установить PowerShellGet в Windows 10, Windows Server 2016, а также любой системе с WMF 5.0, 5.1 или PowerShell 6, выполните следующие команды из сеанса PowerShell с повышенными привилегиями.

```powershell
Install-Module -Name PowerShellGet -Force
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
> PowerShell 3.0 и 4.0 поддерживают только одну версию модуля. Начиная с версии PowerShell 5.0 модули устанавливаются в папку `<modulename>\<version>`. Это позволяет устанавливать несколько версий параллельно. Скачав модуль с помощью `Save-Module`, необходимо скопировать файлы из `<modulename>\<version>` в папку `<modulename>` на целевом компьютере, как показано в приведенных ниже инструкциях.

#### <a name="preparatory-step-on-computers-running-powershell-30"></a>Подготовительные действия на компьютерах с PowerShell 3.0

Инструкции, приведенные в разделах ниже, устанавливают модули в каталоге `$env:ProgramFiles\WindowsPowerShell\Modules`.
В PowerShell 3.0 этот каталог отсутствует в `$env:PSModulePath` по умолчанию, поэтому его необходимо добавить, чтобы модули загружались автоматически. 

Откройте сеанс Windows PowerShell с повышенными привилегиями и выполните в нем следующую команду (действие будет заметно в будущих сеансах).

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>Компьютеры с установленной предварительной версией PackageManagement

> [!NOTE] 
> Предварительная версия PackageManagement была загружаемым компонентом, который обеспечивал доступность PowerShellGet для PowerShell версий 3 и 4, но сейчас он недоступен.
> Чтобы проверить, установлен ли он на данном компьютере, выполните `Get-Module -ListAvailable PowerShellGet`.

1. В сеансе PowerShell используйте `Save-Module`, чтобы скачать текущую версию **PowerShellGet**. Скачиваются две папки: **PowerShellGet** и **PackageManagement**. Каждая папка содержит вложенную папку с номером версии.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Убедитесь, что модули **PowerShellGet** и **PackageManagement** не загружаются в других процессах.

1. Снова откройте консоль PowerShell с повышенными привилегиями, а затем выполните следующую команду.

   ```powershell
   'PowerShellGet', 'PackageManagement' | % { 
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a>Компьютеры без PowerShellGet

Если на компьютере нет какой-либо версии **PowerShellGet** (проверьте это командой `Get-Module -ListAvailable PowerShellGet`), для скачивания модулей необходим компьютер с **PowerShellGet**.

1. На компьютере с установленным **PowerShellGet** используйте `Save-Module`, чтобы скачать текущую версию **PowerShellGet**. Скачиваются две папки: **PowerShellGet** и **PackageManagement**. Каждая папка содержит вложенную папку с номером версии.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Скопируйте соответствующую вложенную папку `<version>` в папках **PowerShellGet** и **PackageManagement** на компьютер, на котором не установлен **PowerShellGet**, в папки `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` и `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` соответственно (требуется сеанс с повышенными правами).
   
1. Например, если у вас есть доступ к папке загрузки на другом компьютере (скажем, `ws1`), с целевого компьютера по UNC-пути (допустим, `\\ws1\C$\LocalFolder`) откройте консоль PowerShell с повышенными правами и выполните следующую команду.

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
