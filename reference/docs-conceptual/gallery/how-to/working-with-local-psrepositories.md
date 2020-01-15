---
ms.date: 11/06/2018
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery,psget
title: Работа с локальными репозиториями PowerShell
ms.openlocfilehash: c1bd905674ae76a3badd3eff50780f0e1bb5fc64
ms.sourcegitcommit: 1b88c280dd0799f225242608f0cbdab485357633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75415825"
---
# <a name="working-with-private-powershellget-repositories"></a>Работа с частными репозиториями PowerShellGet

Модуль PowerShellGet поддерживает репозитории, отличные от коллекции PowerShell.
Эти командлеты реализуют следующие сценарии:

- поддержка надежного, предварительно проверенного набора модулей PowerShell для использования в вашей среде;
- тестирование конвейера CI/CD, который создает модули или скрипты PowerShell;
- предоставление скриптов и модулей PowerShell для систем, которые не имеют доступа к Интернету.
- предоставление скриптов и модулей PowerShell, доступных только для вашей организации.

В этой статье описывается, как настроить локальный репозиторий PowerShell. В статье также рассматривается модуль [OfflinePowerShellGetDeploy][], доступный в коллекции PowerShell. Этот модуль содержит командлеты для установки последней версии PowerShellGet в локальный репозиторий.

## <a name="local-repository-types"></a>Типы локальных репозиториев

Локальный репозиторий PSRepository можно создать в одном из двух видов: в виде сервера NuGet или файлового ресурса. У каждого типа есть свои преимущества и недостатки.

### <a name="nuget-server"></a>Сервер NuGet

| Преимущества| Недостатки |
| --- | --- |
| Точно имитирует функциональность коллекции PowerShell | Многоуровневое приложение требует планирования и поддержки операций |
| NuGet интегрируется с Visual Studio и другими средствами | Требуется модель аутентификации и управление учетными записями NuGet |
| NuGet поддерживает метаданные в пакетах `.Nupkg` | Публикация требует управления ключами API и их обслуживания |
| Возможность поиска, администрирования пакетов и т. д. | |

### <a name="file-share"></a>Общая папка

| Преимущества| Недостатки |
| --- | --- |
| Простота установки, резервного копирования и обслуживания | Метаданные, используемые PowerShellGet, недоступны |
| Простая модель безопасности: разрешения пользователей задаются для файлового ресурса | Отсутствие интерфейса пользователя за пределами основного файлового ресурса |
| Нет ограничений, таких как замена существующих элементов | Ограниченная безопасность и отсутствие записей о том, кто и что обновляет |

PowerShellGet работает с любыми типами элементов и поддерживает поиск версий и установку зависимостей.
Однако некоторые функции, которые работают в коллекции PowerShell, недоступны для базовых серверов NuGet или файловых ресурсов.

- Все элементы представлены в виде пакетов без разграничения скриптов, модулей, ресурсов DSC или возможностей ролей.
- Файловые ресурсы не могут распознавать метаданные пакета, включая теги.

## <a name="creating-a-local-repository"></a>Создание локального репозитория

В статье по следующей ссылке перечислены действия по настройке собственного сервера NuGet.

- [NuGet.Server][]

Следуйте инструкциям до момента добавления пакетов. Действия по [публикации пакета](#publishing-to-a-local-repository) описаны далее в этой статье.

При использовании репозитория на основе файлового ресурса убедитесь, что у ваших пользователей есть разрешения на доступ к файловому ресурсу.

## <a name="registering-a-local-repository"></a>Регистрация локального репозитория

Прежде чем репозиторий можно будет использовать, его необходимо зарегистрировать с помощью команды `Register-PSRepository`.
В приведенных ниже примерах для параметра **InstallationPolicy** установлено значение *Trusted* (предполагается, что вы доверяете собственному репозиторию).

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

Обратите внимание на разницу между тем, как две команды обрабатывают параметр **ScriptSourceLocation**. Для репозиториев на основе файлового ресурса значения параметров **SourceLocation** и **ScriptSourceLocation** должны совпадать. Для веб-репозиториев они должны отличаться, поэтому в этом примере в параметр **SourceLocation** добавлен завершающий символ "/".

Если вы хотите, чтобы созданный репозиторий PSRepository был репозиторием по умолчанию, необходимо отменить регистрацию всех остальных репозиториев PowerShell. Пример:

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> Имя репозитория PSGallery зарезервировано для использования в коллекции PowerShell. Регистрацию PSGallery можно отменить, но нельзя повторно использовать имя PSGallery для любого другого репозитория.

Если вам нужно восстановить регистрацию PSGallery, выполните следующую команду:

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a>Публикация в локальном репозитории

После того, как вы зарегистрировали локальный репозиторий PSRepository, вы можете выполнять в нем публикации. Существует два основных сценария публикации: публикация собственного модуля и публикация модуля из репозитория PSGallery.

### <a name="publishing-a-module-you-authored"></a>Публикация созданного вами модуля

Чтобы опубликовать свой модуль в своем локальном репозитории PSRepository так же, как вы делаете это для коллекции PowerShell, используйте командлеты `Publish-Module` и `Publish-Script`.

- Укажите расположение для своего кода.
- Предоставьте ключ API.
- Укажите имя репозитория. Например `-PSRepository LocalPSRepo`.

> [!NOTE]
> Необходимо создать учетную запись на сервере NuGet, а затем войти в систему, чтобы создать и сохранить ключ API.
> При использовании файлового ресурса для значения NuGetApiKey укажите любую непустую строку.

Примеры:

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'
```

```powershell
# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> Чтобы обеспечить безопасность, ключи API не следует жестко программировать в скриптах. Используйте безопасную систему управления ключами.

### <a name="publishing-a-module-from-the-psgallery"></a>Публикация модуля из PSGallery

Чтобы опубликовать модуль из PSGallery в локальном репозитории PSRepository, вы можно использовать командлет Save-Package.

- Укажите имя пакета.
- Укажите NuGet в качестве поставщика.
- Укажите расположение PSGallery в качестве источника (https://www.powershellgallery.com/api/v2) ).
- Укажите путь к вашему локальному репозиторию.

Пример

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider NuGet -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

Если ваш локальный репозиторий PSRepository имеет веб-интерфейс, для него требуется дополнительный шаг, на котором выполняется публикация с помощью nuget.exe.

См. документацию по использованию [nuget.exe][].

## <a name="installing-powershellget-on-a-disconnected-system"></a>Установка PowerShellGet в отключенной системе

Развертывание PowerShellGet затруднено в средах, где требуется отключение систем от Интернета. PowerShellGet имеет процесс начальной загрузки, который устанавливает последнюю версию при первом использовании. Модуль OfflinePowerShellGetDeploy в коллекции PowerShell предоставляет командлеты, которые поддерживают этот процесс начальной загрузки.

Чтобы выполнить начальную загрузку автономного развертывания, необходимо следующее:

- Скачайте и установите OfflinePowerShellGetDeploy в вашей подключенной к Интернету и отключенных системах.
- Скачайте PowerShellGet и его зависимости на подключенную к Интернету систему с помощью командлета `Save-PowerShellGetForOffline`.
- Скопируйте PowerShellGet и его зависимости из подключенной к Интернету системы в отключенную систему.
- Чтобы поместить PowerShellGet и его зависимости в соответствующие папки, используйте командлет `Install-PowerShellGetOffline` в отключенной системе.

Следующие команды используют `Save-PowerShellGetForOffline`, чтобы поместить все компоненты в папку `f:\OfflinePowerShellGet`.

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

На этом этапе необходимо сделать содержимое `F:\OfflinePowerShellGet` доступным для ваших отключенных систем. Запустите командлет `Install-PowerShellGetOffline`, чтобы установить PowerShellGet в отключенной системе.

> [!NOTE]
> Важно, чтобы вы не запускали PowerShellGet в сеансе PowerShell перед выполнением этих команд. После загрузки модуля PowerShellGet в сеанс компоненты невозможно обновить. Если вы по ошибке запустили PowerShellGet, закройте и перезапустите PowerShell.

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

После выполнения этих команд вы сможете опубликовать модуль PowerShellGet в своем локальном репозитории.

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

## <a name="use-packaging-solutions-to-host-powershellget-repositories"></a>Использование решений упаковки для размещения репозиториев PowerShellGet

Вы также можете использовать такие решения упаковки, как Azure Artifacts, для размещения частного или общедоступного репозитория PowerShellGet. Дополнительные сведения и инструкции см. в [документации по Azure Artifacts](https://docs.microsoft.com/azure/devops/artifacts/tutorials/private-powershell-library).

> [!IMPORTANT]
> Чтобы обеспечить безопасность, ключи API не следует жестко программировать в скриптах. Используйте безопасную систему управления ключами.

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[NuGet.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
