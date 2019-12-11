---
ms.date: 10/17/2017
contributor: keithb
keywords: коллекция,powershell,командлет,psget
title: Предварительные версии сценариев
ms.openlocfilehash: c0198c2f575d2c004949ccebab49d93ce54716be
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328485"
---
# <a name="prerelease-versions-of-scripts"></a>Предварительные версии сценариев

Начиная с версии 1.6.0, PowerShellGet и коллекция PowerShell поддерживают маркировку версий с номерами выше 1.0.0 как предварительных. До этого номера предварительных версий пакетов должны были обязательно начинаться с 0. Такая возможность добавлена, чтобы улучшить поддержку соглашения о версиях [SemVer 1.0.0](http://semver.org/spec/v1.0.0.html) и при этом сохранить обратную совместимость с PowerShell версий 3 и выше, а также с текущими версиями PowerShellGet. Этот раздел описывает особенности присвоения версий сценариям. Аналогичные возможности для модулей см. в разделе [Предварительные версии модулей](module-prerelease-support.md). Благодаря этой возможности издатель может присвоить своему сценарию предварительную версию 2.5.0-alpha, а затем выпустить готовую к использованию версию 2.5.0, которая заменит предварительную.

На высоком уровне возможности для предварительных версий сценариев включают:

- добавление суффикса PrereleaseString в строку версии в манифесте сценария. При публикации скриптов в коллекцию PowerShell эти данные извлекаются из манифеста и используются для определения предварительных версий пакетов.
- Для получения предварительных версий пакетов необходимо добавить флаг -AllowPrerelease к таким командам PowerShellGet, как Find-Script, Install-Script, Update-Script и Save-Script. Если этот флаг не указан, предварительные версии не будут отображаться.
- Версии сценариев, отображаемые командлетами Find-Script и Get-InstalledScript, а также версии в коллекции PowerShell будут отображаться с параметром PrereleaseString, например: 2.5.0-alpha.

Ниже приведено подробное описание этих возможностей.

## <a name="identifying-a-script-version-as-a-prerelease"></a>Определение версии сценария как предварительной

Реализация предварительных версий в PowerShellGet для сценариев проще, чем для модулей. Контроль версий сценариев поддерживается только в PowerShellGet, поэтому добавление суффикса к номеру предварительной версии не вызовет проблем совместимости. Для определения версии сценария в коллекции PowerShell как предварительной, добавьте суффикс предварительной версии к правильно сформированной строке версии в метаданных сценария.

Пример манифеста сценария с предварительной версией

```powershell
<#PSScriptInfo

.VERSION 3.2.1-alpha12

.GUID

...

#>
```

Для использования суффикса предварительной версии строка версии должна удовлетворять следующим условиям.

- Суффикс предварительной версии можно указать, только если версия состоит из трех сегментов в виде <основная_версия>.<дополнительная_версия>.<сборка>.
  Это соответствует соглашению о версиях SemVer 1.0.0.
- Суффикс предварительной версии — это строка, которая начинается с дефиса и может содержать буквенно-цифровые символы ASCII [0-9A-Za-z-].
- В настоящий момент поддерживается только SemVer версии 1.0.0, поэтому суффикс предварительной версии **не должен** содержать ни точек, ни символов + [.+], которые допустимы в SemVer 2.0.
- Пример допустимых строк PrereleaseString: -alpha, -alpha1, -BETA, -update20171020

### <a name="prerelease-versioning-impact-on-sort-order-and-installation-folders"></a>Влияние предварительных версий на порядок сортировки и установочные папки

При использовании предварительных версий изменяется порядок сортировки, что имеет значение при публикации сценариев в коллекции PowerShell и при установке сценариев с помощью команд PowerShellGet. Если существует две версии сценария с одним номером, то сортировка производится по части строки, следующей после дефиса. Таким образом версия 2.5.0-alpha меньше, чем 2.5.0-beta, а последняя меньше, чем 2.5.0-gamma. Если два сценария имеют одинаковый номер версии и только у одного из них есть строка PrereleaseString, то готовым к использованию будет считаться сценарий **без** суффикса предварительной версии и при сортировке он будет указываться, как имеющий более высокую версию по отношению к предварительной. Например: при сравнении версий 2.5.0 и 2.5.0-beta, будет считаться, что версия 2.5.0 имеет больший номер.

По умолчанию при публикации в коллекцию PowerShell новый сценарий обязательно должен иметь более высокую версию, чем все сценарии, опубликованные ранее. Издатель может обновить версию 2.5.0-alpha версией 2.5.0-beta или 2.5.0 (без суффикса предварительной версии).

## <a name="finding-and-acquiring-prerelease-packages-using-powershellget-commands"></a>Поиск и получение предварительных версий пакетов с помощью команд PowerShellGet

Для работы с предварительными версиями пакетов с помощью таких команд PowerShellGet, как Find-Script, Install-Script, Update-Script и Save-Script, необходимо добавлять флаг -AllowPrerelease. Если флаг -AllowPrerelease указан, в результат выполнения команды будут включены доступные предварительные версии пакетов. Если флаг -AllowPrerelease не указан, предварительные версии не будут отображаться.

Единственным исключением является команда Get-InstalledScript и в некоторых случаях команда Uninstall-Script.

- Команда Get-InstalledScript всегда автоматически отображает информацию о предварительных версиях в строке версии при ее наличии.
- Если **номер версии не указан**, то по умолчанию команда Uninstall-Script удалит самую последнюю версию сценария. Такое поведение команды осталось неизменным. Если предварительная версия указана с помощью `-RequiredVersion`, необходимо также указать `-AllowPrerelease`.

## <a name="examples"></a>Примеры

```powershell
# Assume the PowerShell Gallery has TestPackage versions 1.8.0 and 1.9.0-alpha.
# If -AllowPrerelease is not specified, only version 1.8.0 will be returned.
C:\windows\system32> Find-Script TestPackage

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.8.0          TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> Find-Script TestPackage -AllowPrerelease

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.9.0-alpha    TestPackage                         PSGallery            Package used to validate changes to PowerShe...

# To install a prerelease, you must specify -AllowPrerelease. Specifying a prerelease version string is not sufficient.

C:\windows\system32> Install-Script TestPackage -RequiredVersion 1.9.0-alpha

PackageManagement\Find-Package : No match was found for the specified search criteria and script name 'TestPackage'.
Try Get-PSRepository to see all available registered script repositories.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PSModule.psm1:1455 char:3
+         PackageManagement\Find-Package @PSBoundParameters | Microsoft ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Microsoft.Power...ets.FindPackage:FindPackage)[Find-Package], Exception
    + FullyQualifiedErrorId : NoMatchFoundForCriteria,Microsoft.PowerShell.PackageManagement.Cmdlets.FindPackage

# The previous command failed because -AllowPrerelease was not specified.
# Adding -AllowPrerelease will result in success.

C:\windows\system32> Install-Script TestPackage -RequiredVersion 1.9.0-alpha -AllowPrerelease
C:\windows\system32> Get-InstalledScript TestPackage

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to PowerShe...

# Note that Get-InstalledScript shows the prerelease version.
# If -RequiredVersion is not specified, all installed scripts will be displayed by Get-InstalledScript
```

Если не задан флаг -RequiredVersion, то команда Uninstall-Script удалит текущую версию сценария.
Если в параметре -RequiredVersion указана предварительная версия, то необходимо обязательно добавить к команде флаг -AllowPrerelease.

``` powershell
C:\windows\system32> Get-InstalledScript TestPackage

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to PowerShe...

C:\windows\system32> Uninstall-Script TestPackage -RequiredVersion 1.9.0-alpha
Uninstall-Script: The '-AllowPrerelease' parameter must be specified when using the Prerelease string in
MinimumVersion, MaximumVersion, or RequiredVersion.
At line:1 char:1
+ Uninstall-Script TestPackage -RequiredVersion 1.9.0-beta
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Uninstall-Script], ArgumentException
    + FullyQualifiedErrorId : AllowPrereleaseRequiredToUsePrereleaseStringInVersion,Uninstall-script


C:\windows\system32> Uninstall-Script TestPackage -RequiredVersion 1.9.0-alpha -AllowPrerelease
# Since script versions are not installed side-by-side, the above could be simply "Uninstall-Script TestPackage"

C:\windows\system32> Get-Installedscript TestPackage
PackageManagement\Get-Package : No match was found for the specified search criteria and script names 'testpackage'.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.5.0.0\PSModule.psm1:4088 char:9
+         PackageManagement\Get-Package @PSBoundParameters | Microsoft. ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Microsoft.Power...lets.GetPackage:GetPackage) [Get-Package], Exception
    + FullyQualifiedErrorId : NoMatchFound,Microsoft.PowerShell.PackageManagement.Cmdlets.GetPackage
```

## <a name="more-details"></a>Дополнительные подробности

- [Предварительные версии модулей](module-prerelease-support.md)
- [Find-Script](/powershell/module/powershellget/find-script)
- [Install-Script](/powershell/module/powershellget/install-script)
- [Save-Script](/powershell/module/powershellget/save-script)
- [Update-Script](/powershell/module/powershellget/update-script)
- [Get-InstalledScript](/powershell/module/powershellget/get-installedscript)
- [Uninstall-Script](/powershell/module/powershellget/uninstall-script)
