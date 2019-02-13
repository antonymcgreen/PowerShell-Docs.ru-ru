---
ms.date: 11/06/2018
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery,psget
title: Работа с локального PSRepositories
ms.openlocfilehash: 94824ea584c097838b24c6f2cd02407b6147a781
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55682674"
---
# <a name="working-with-local-powershellget-repositories"></a>Работа с локальными хранилищами PowerShellGet

Поддержка модуля PowerShellGet репозитории отличный от коллекции PowerShell.
Эти командлеты реализации следующих сценариев:

- Поддерживает набор доверенных, предварительно проверенных модулей PowerShell для использования в вашей среде
- Тестирование конвейера CI/CD, который создает модули PowerShell или сценариев
- Доставлять сценариев и модулей PowerShell системы, для которых не удается получить доступ к Интернету

В этой статье описывается настройка локального репозитория PowerShell. В статье также описаны [OfflinePowerShellGetDeploy][] модуль из коллекции PowerShell. Этот модуль содержит командлеты, чтобы установить последнюю версию PowerShellGet в локальный репозиторий.

## <a name="local-repository-types"></a>Типы локального репозитория

Существует два способа для создания локального PSRepository: NuGet server или файловый ресурс. Каждый тип имеет преимущества и недостатки:

NuGet Server

| Преимущества| Недостатки |
| --- | --- |
| Точно имитирует функциональность PowerShellGallery | Многоуровневое приложение требует планирования операций и поддержка |
| NuGet интегрируется с Visual Studio и другие средства | Модель проверки подлинности и контроля учетных записей NuGet |
| NuGet поддерживает метаданные в `.Nupkg` пакетов | Публикации требуется ключ API управление и обслуживание |
| Предоставляет поиска, пакет администрирования и т. д. | |

Общая папка

| Преимущества| Недостатки |
| --- | --- |
| Легко настроить, резервное копирование и поддерживать | Метаданные, используемые PowerShellGet недоступна |
| Модель безопасности — разрешения пользователя в общей папке | Ни один пользовательский Интерфейс за пределы базовый файловый ресурс |
| Без ограничений, таких как замена существующих элементов | Нет записи, от тех, кто обновляет новые и ограниченной безопасностью |

PowerShellGet работает с типом и поддерживает поиск версии и установка зависимостей.
Тем не менее некоторые функции работают для коллекции PowerShell недоступны для базового NuGet серверов или общих папок.

- Все, что является пакетом - никакой разницы, сценарии, модули, ресурсы DSC и возможности ролей.
- Файловые серверы общего ресурса не могут видеть метаданные пакета, включая теги.

## <a name="creating-a-local-repository"></a>Создание локального репозитория

В следующей статье перечислены шаги по настройке сервера NuGet.

- [NuGet.Server][]

Следуйте инструкциям вплоть до добавления пакетов. Действия по [публикации пакета](#publishing-to-a-local-repository) рассматриваются далее в этой статье.

Для репозитория основе общих файлов убедитесь, что у пользователей есть разрешения на доступ к общей папке.

## <a name="registering-a-local-repository"></a>Регистрация локального репозитория

Прежде чем можно будет использовать репозиторий, его необходимо зарегистрировать с помощью `Register-PSRepository` команды.
В приведенных ниже примерах **InstallationPolicy** присваивается *надежных*, на предположении, что вы доверяете ваш собственный репозиторий.

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

Запишите разницу между порядок обработки двух команд **ScriptSourceLocation**. Для файла ресурса репозиториев на основе **SourceLocation** и **ScriptSourceLocation** должны совпадать. Для репозитория на основе веб технологий, они должны быть разными, поэтому в этом примере символ «/» добавляется **SourceLocation**.

Если требуется только что созданный PSRepository быть репозитория по умолчанию, необходимо отменить регистрацию всех PSRepositories. Например:

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> Имя репозитория «PSGallery» зарезервирован для использования в коллекции PowerShell. Вы можете отменить регистрацию PSGallery, но нельзя повторно использовать имя PSGallery для другого репозитория.

Если необходимо восстановить PSGallery, выполните следующую команду:

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a>Публикации в локальном репозитории

После регистрации локального PSRepository, можно опубликовать ваш локальный PSRepository. Существует два основных сценария публикации: публикация собственных модулей и публикации модуля из PSGallery.

### <a name="publishing-a-module-you-authored"></a>Для публикации модуля, созданные

Используйте `Publish-Module` и `Publish-Script` для публикации модуля в вашей локальной PSRepository так же, как и для коллекции PowerShell.

- Укажите расположение для кода
- Укажите ключ API
- Укажите имя репозитория. Например: `-PSRepository LocalPSRepo`

> [!NOTE]
> Необходимо создать учетную запись на сервере NuGet, а затем войдите в для создания и сохранения ключ API.
> Для файлового ресурса используйте любой непустой строкой для NuGetApiKey значения.

Примеры

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> Чтобы обеспечить безопасность, ключи API не следует жестко заданное в сценарии. Используйте систему безопасное управление ключами.

### <a name="publishing-a-module-from-the-psgallery"></a>Публикация модуля из PSGallery

Чтобы опубликовать модуль из PSGallery к вашей локальной PSRepository, можно использовать командлет «Save-Package».

- Укажите имя пакета
- Укажите «NuGet» в качестве поставщика
- Укажите расположение PSGallery в качестве источника)https://www.powershellgallery.com/api/v2)
- Укажите путь к локального репозитория

Пример:

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider Nuget -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

Если ваш локальный PSRepository веб интерфейсом, то требуется дополнительный шаг, который использует nuget.exe для публикации.

См. в документации по использованию [nuget.exe][].

## <a name="installing-powershellget-on-a-disconnected-system"></a>Установка PowerShellGet в отключенной системе

Развертывание PowerShellGet сложно в средах, требующих систем, чтобы быть отключен от Интернета. С помощью PowerShellGet процесс начальной загрузки, который устанавливает последнюю версию при первом использовании. Модуль OfflinePowerShellGetDeploy в коллекции PowerShell предоставляет командлеты, поддерживающие этот процесс начальной загрузки.

Чтобы выполнить начальную загрузку развертывания в автономном режиме, вам потребуется:

- Скачайте и установите системы OfflinePowerShellGetDeploy вашей подключенной к Интернету и отключенных систем
- Скачайте PowerShellGet и его зависимостей в системе, подключенной к Интернету с помощью `Save-PowerShellGetForOffline` командлета
- Скопируйте PowerShellGet и его зависимости из системы, подключенной к Интернету в отключенной системе
- Используйте `Install-PowerShellGetOffline` в отключенной системе, чтобы поместить PowerShellGet и его зависимости в нужные папки

Следующие команды используют `Save-PowerShellGetForOffline` для размещения всех компонентов в папку `f:\OfflinePowerShellGet`

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

На этом этапе необходимо сделать содержимое `F:\OfflinePowerShellGet` для отключенных систем. Запустите `Install-PowerShellGetOffline` командлет, чтобы установить PowerShellGet в отключенной системе.

> [!NOTE]
> Очень важно, что не выполнять PowerShellGet в сеансе PowerShell перед выполнением этих команд. После загрузки PowerShellGet в сеанс не удается обновить компоненты. При запуске PowerShellGet по ошибке, закройте и перезапустите PowerShell.

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

После выполнения этих команд, все готово для публикации PowerShellGet в локальном репозитории.

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> Чтобы обеспечить безопасность, ключи API не следует жестко заданное в сценарии. Используйте систему безопасное управление ключами.

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
