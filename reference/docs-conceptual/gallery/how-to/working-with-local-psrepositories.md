---
ms.date: 11/06/2018
title: Работа с локальными репозиториями PowerShell
description: Модуль PowerShellGet поддерживает репозитории, отличные от коллекции PowerShell. В этой статье описывается, как настроить локальный репозиторий PowerShell.
ms.openlocfilehash: 24a2fd23124b3897952d64a347d103d9ee10248f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662348"
---
# <a name="working-with-private-powershellget-repositories"></a><span data-ttu-id="ef061-104">Работа с частными репозиториями PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="ef061-104">Working with Private PowerShellGet Repositories</span></span>

<span data-ttu-id="ef061-105">Модуль PowerShellGet поддерживает репозитории, отличные от коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef061-105">The PowerShellGet module support repositories other than the PowerShell Gallery.</span></span>
<span data-ttu-id="ef061-106">Эти командлеты реализуют следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="ef061-106">These cmdlets enable the following scenarios:</span></span>

- <span data-ttu-id="ef061-107">поддержка надежного, предварительно проверенного набора модулей PowerShell для использования в вашей среде;</span><span class="sxs-lookup"><span data-stu-id="ef061-107">Support a trusted, pre-validated set of PowerShell modules for use in your environment</span></span>
- <span data-ttu-id="ef061-108">тестирование конвейера CI/CD, который создает модули или скрипты PowerShell;</span><span class="sxs-lookup"><span data-stu-id="ef061-108">Testing a CI/CD pipeline that builds PowerShell modules or scripts</span></span>
- <span data-ttu-id="ef061-109">предоставление скриптов и модулей PowerShell для систем, которые не имеют доступа к Интернету.</span><span class="sxs-lookup"><span data-stu-id="ef061-109">Deliver PowerShell scripts and modules to systems that can't access the internet</span></span>
- <span data-ttu-id="ef061-110">предоставление скриптов и модулей PowerShell, доступных только для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ef061-110">Deliver PowerShell scripts and modules only available to your organization</span></span>

<span data-ttu-id="ef061-111">В этой статье описывается, как настроить локальный репозиторий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef061-111">This article describes how to set up a local PowerShell repository.</span></span> <span data-ttu-id="ef061-112">В статье также рассматривается модуль [OfflinePowerShellGetDeploy][], доступный в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef061-112">The article also covers the [OfflinePowerShellGetDeploy][] module available from the PowerShell Gallery.</span></span> <span data-ttu-id="ef061-113">Этот модуль содержит командлеты для установки последней версии PowerShellGet в локальный репозиторий.</span><span class="sxs-lookup"><span data-stu-id="ef061-113">This module contains cmdlets to install the latest version of PowerShellGet into your local repository.</span></span>

## <a name="local-repository-types"></a><span data-ttu-id="ef061-114">Типы локальных репозиториев</span><span class="sxs-lookup"><span data-stu-id="ef061-114">Local repository types</span></span>

<span data-ttu-id="ef061-115">Локальный репозиторий PSRepository можно создать в одном из двух видов: в виде сервера NuGet или файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="ef061-115">There are two ways to create a local PSRepository: NuGet server or file share.</span></span> <span data-ttu-id="ef061-116">У каждого типа есть свои преимущества и недостатки.</span><span class="sxs-lookup"><span data-stu-id="ef061-116">Each type has advantages and disadvantages:</span></span>

### <a name="nuget-server"></a><span data-ttu-id="ef061-117">Сервер NuGet</span><span class="sxs-lookup"><span data-stu-id="ef061-117">NuGet Server</span></span>

| <span data-ttu-id="ef061-118">Преимущества</span><span class="sxs-lookup"><span data-stu-id="ef061-118">Advantages</span></span>| <span data-ttu-id="ef061-119">Недостатки</span><span class="sxs-lookup"><span data-stu-id="ef061-119">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="ef061-120">Точно имитирует функциональность коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef061-120">Closely mimics PowerShellGallery functionality</span></span> | <span data-ttu-id="ef061-121">Многоуровневое приложение требует планирования и поддержки операций</span><span class="sxs-lookup"><span data-stu-id="ef061-121">Multi-tier app requires operations planning & support</span></span> |
| <span data-ttu-id="ef061-122">NuGet интегрируется с Visual Studio и другими средствами</span><span class="sxs-lookup"><span data-stu-id="ef061-122">NuGet integrates with Visual Studio, other tools</span></span> | <span data-ttu-id="ef061-123">Требуется модель аутентификации и управление учетными записями NuGet</span><span class="sxs-lookup"><span data-stu-id="ef061-123">Authentication model and NuGet accounts management needed</span></span> |
| <span data-ttu-id="ef061-124">NuGet поддерживает метаданные в пакетах `.Nupkg`</span><span class="sxs-lookup"><span data-stu-id="ef061-124">NuGet supports metadata in `.Nupkg` packages</span></span> | <span data-ttu-id="ef061-125">Публикация требует управления ключами API и их обслуживания</span><span class="sxs-lookup"><span data-stu-id="ef061-125">Publishing requires API Key management & maintenance</span></span> |
| <span data-ttu-id="ef061-126">Возможность поиска, администрирования пакетов и т. д.</span><span class="sxs-lookup"><span data-stu-id="ef061-126">Provides search, package administration, etc.</span></span> | |

### <a name="file-share"></a><span data-ttu-id="ef061-127">Общая папка</span><span class="sxs-lookup"><span data-stu-id="ef061-127">File Share</span></span>

| <span data-ttu-id="ef061-128">Преимущества</span><span class="sxs-lookup"><span data-stu-id="ef061-128">Advantages</span></span>| <span data-ttu-id="ef061-129">Недостатки</span><span class="sxs-lookup"><span data-stu-id="ef061-129">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="ef061-130">Простота установки, резервного копирования и обслуживания</span><span class="sxs-lookup"><span data-stu-id="ef061-130">Easy to set up, back up, and maintain</span></span> | <span data-ttu-id="ef061-131">Метаданные, используемые PowerShellGet, недоступны</span><span class="sxs-lookup"><span data-stu-id="ef061-131">Metadata used by PowerShellGet isn't available</span></span> |
| <span data-ttu-id="ef061-132">Простая модель безопасности: разрешения пользователей задаются для файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="ef061-132">Simple security model - user permissions on the share</span></span> | <span data-ttu-id="ef061-133">Отсутствие интерфейса пользователя за пределами основного файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="ef061-133">No UI beyond basic file share</span></span> |
| <span data-ttu-id="ef061-134">Нет ограничений, таких как замена существующих элементов</span><span class="sxs-lookup"><span data-stu-id="ef061-134">No constraints such as replacing existing items</span></span> | <span data-ttu-id="ef061-135">Ограниченная безопасность и отсутствие записей о том, кто и что обновляет</span><span class="sxs-lookup"><span data-stu-id="ef061-135">Limited security and no recording of who updates what</span></span> |

<span data-ttu-id="ef061-136">PowerShellGet работает с любыми типами элементов и поддерживает поиск версий и установку зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ef061-136">PowerShellGet works with either type and supports locating versions and dependency installation.</span></span>
<span data-ttu-id="ef061-137">Однако некоторые функции, которые работают в коллекции PowerShell, недоступны для базовых серверов NuGet или файловых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ef061-137">However, some features that work for the PowerShell Gallery aren't available for base NuGet servers or file shares.</span></span>

- <span data-ttu-id="ef061-138">Все элементы представлены в виде пакетов без разграничения скриптов, модулей, ресурсов DSC или возможностей ролей.</span><span class="sxs-lookup"><span data-stu-id="ef061-138">Everything is a package - no differentiation of scripts, modules, DSC resources, or role capabilities.</span></span>
- <span data-ttu-id="ef061-139">Файловые ресурсы не могут распознавать метаданные пакета, включая теги.</span><span class="sxs-lookup"><span data-stu-id="ef061-139">File share servers can't see package metadata, including tags.</span></span>

## <a name="creating-a-local-repository"></a><span data-ttu-id="ef061-140">Создание локального репозитория</span><span class="sxs-lookup"><span data-stu-id="ef061-140">Creating a local repository</span></span>

<span data-ttu-id="ef061-141">В статье по следующей ссылке перечислены действия по настройке собственного сервера NuGet.</span><span class="sxs-lookup"><span data-stu-id="ef061-141">The following article lists the steps for setting up your own NuGet Server.</span></span>

- <span data-ttu-id="ef061-142">[NuGet.Server][]</span><span class="sxs-lookup"><span data-stu-id="ef061-142">[NuGet.Server][]</span></span>

<span data-ttu-id="ef061-143">Следуйте инструкциям до момента добавления пакетов.</span><span class="sxs-lookup"><span data-stu-id="ef061-143">Follow the steps up to the point of adding packages.</span></span> <span data-ttu-id="ef061-144">Действия по [публикации пакета](#publishing-to-a-local-repository) описаны далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ef061-144">The steps for [publishing a package](#publishing-to-a-local-repository) are covered later in this article.</span></span>

<span data-ttu-id="ef061-145">При использовании репозитория на основе файлового ресурса убедитесь, что у ваших пользователей есть разрешения на доступ к файловому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="ef061-145">For a file share-based repository, make sure that your users have permissions to access the file share.</span></span>

## <a name="registering-a-local-repository"></a><span data-ttu-id="ef061-146">Регистрация локального репозитория</span><span class="sxs-lookup"><span data-stu-id="ef061-146">Registering a local repository</span></span>

<span data-ttu-id="ef061-147">Прежде чем репозиторий можно будет использовать, его необходимо зарегистрировать с помощью команды `Register-PSRepository`.</span><span class="sxs-lookup"><span data-stu-id="ef061-147">Before a repository can be used, it must be registered using the `Register-PSRepository` command.</span></span>
<span data-ttu-id="ef061-148">В приведенных ниже примерах для параметра **InstallationPolicy** установлено значение *Trusted* (предполагается, что вы доверяете собственному репозиторию).</span><span class="sxs-lookup"><span data-stu-id="ef061-148">In the examples below, the **InstallationPolicy** is set to *Trusted* , on the assumption that you trust your own repository.</span></span>

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

<span data-ttu-id="ef061-149">Обратите внимание на разницу между тем, как две команды обрабатывают параметр **ScriptSourceLocation** .</span><span class="sxs-lookup"><span data-stu-id="ef061-149">Take note of the difference between how the two commands handle **ScriptSourceLocation** .</span></span> <span data-ttu-id="ef061-150">Для репозиториев на основе файлового ресурса значения параметров **SourceLocation** и **ScriptSourceLocation** должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="ef061-150">For a file share-based repositories, the **SourceLocation** and **ScriptSourceLocation** must match.</span></span> <span data-ttu-id="ef061-151">Для веб-репозиториев они должны отличаться, поэтому в этом примере в параметр **SourceLocation** добавлен завершающий символ "/".</span><span class="sxs-lookup"><span data-stu-id="ef061-151">For a web-based repository, they must be different, so in this example a trailing "/" is added to the **SourceLocation** .</span></span>

<span data-ttu-id="ef061-152">Если вы хотите, чтобы созданный репозиторий PSRepository был репозиторием по умолчанию, необходимо отменить регистрацию всех остальных репозиториев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef061-152">If you want the newly created PSRepository to be the default repository, you must unregister all other PSRepositories.</span></span> <span data-ttu-id="ef061-153">Пример:</span><span class="sxs-lookup"><span data-stu-id="ef061-153">For example:</span></span>

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> <span data-ttu-id="ef061-154">Имя репозитория PSGallery зарезервировано для использования в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef061-154">The repository name 'PSGallery' is reserved for use by the PowerShell Gallery.</span></span> <span data-ttu-id="ef061-155">Регистрацию PSGallery можно отменить, но нельзя повторно использовать имя PSGallery для любого другого репозитория.</span><span class="sxs-lookup"><span data-stu-id="ef061-155">You can unregister PSGallery, but you cannot reuse the name PSGallery for any other repository.</span></span>

<span data-ttu-id="ef061-156">Если вам нужно восстановить регистрацию PSGallery, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ef061-156">If you need to restore the PSGallery, run the following command:</span></span>

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a><span data-ttu-id="ef061-157">Публикация в локальном репозитории</span><span class="sxs-lookup"><span data-stu-id="ef061-157">Publishing to a local repository</span></span>

<span data-ttu-id="ef061-158">После того, как вы зарегистрировали локальный репозиторий PSRepository, вы можете выполнять в нем публикации.</span><span class="sxs-lookup"><span data-stu-id="ef061-158">Once you've registered the local PSRepository, you can publish to your local PSRepository.</span></span> <span data-ttu-id="ef061-159">Существует два основных сценария публикации: публикация собственного модуля и публикация модуля из репозитория PSGallery.</span><span class="sxs-lookup"><span data-stu-id="ef061-159">There are two main publishing scenarios: publishing your own module and publishing a module from the PSGallery.</span></span>

### <a name="publishing-a-module-you-authored"></a><span data-ttu-id="ef061-160">Публикация созданного вами модуля</span><span class="sxs-lookup"><span data-stu-id="ef061-160">Publishing a module you authored</span></span>

<span data-ttu-id="ef061-161">Чтобы опубликовать свой модуль в своем локальном репозитории PSRepository так же, как вы делаете это для коллекции PowerShell, используйте командлеты `Publish-Module` и `Publish-Script`.</span><span class="sxs-lookup"><span data-stu-id="ef061-161">Use `Publish-Module` and `Publish-Script` to publish your module to your local PSRepository the same way you do for the PowerShell Gallery.</span></span>

- <span data-ttu-id="ef061-162">Укажите расположение для своего кода.</span><span class="sxs-lookup"><span data-stu-id="ef061-162">Specify the location for your code</span></span>
- <span data-ttu-id="ef061-163">Предоставьте ключ API.</span><span class="sxs-lookup"><span data-stu-id="ef061-163">Supply an API key</span></span>
- <span data-ttu-id="ef061-164">Укажите имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="ef061-164">Specify the repository name.</span></span> <span data-ttu-id="ef061-165">Например `-PSRepository LocalPSRepo`.</span><span class="sxs-lookup"><span data-stu-id="ef061-165">For example, `-PSRepository LocalPSRepo`</span></span>

> [!NOTE]
> <span data-ttu-id="ef061-166">Необходимо создать учетную запись на сервере NuGet, а затем войти в систему, чтобы создать и сохранить ключ API.</span><span class="sxs-lookup"><span data-stu-id="ef061-166">You must create an account in the NuGet server, then sign in to generate and save the API key.</span></span>
> <span data-ttu-id="ef061-167">При использовании файлового ресурса для значения NuGetApiKey укажите любую непустую строку.</span><span class="sxs-lookup"><span data-stu-id="ef061-167">For a file share, use any non-blank string for the NuGetApiKey value.</span></span>

<span data-ttu-id="ef061-168">Примеры:</span><span class="sxs-lookup"><span data-stu-id="ef061-168">Examples:</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey $nuGetApiKey
```

> [!IMPORTANT]
> <span data-ttu-id="ef061-169">Чтобы обеспечить безопасность, ключи API не следует жестко программировать в скриптах.</span><span class="sxs-lookup"><span data-stu-id="ef061-169">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="ef061-170">Используйте безопасную систему управления ключами.</span><span class="sxs-lookup"><span data-stu-id="ef061-170">Use a secure key management system.</span></span> <span data-ttu-id="ef061-171">При выполнении команды вручную ключи API не должны передаваться как обычный текст, чтобы избежать записи в журнал. Для безопасной передачи значения ключа API можно использовать командлет `Read-Host`.</span><span class="sxs-lookup"><span data-stu-id="ef061-171">When executing a command manually, API keys should not be passed as plain-text to avoid it being logged, the `Read-Host` cmdlet can be used to safely pass the value of the API key.</span></span>

```powershell
# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

### <a name="publishing-a-module-from-the-psgallery"></a><span data-ttu-id="ef061-172">Публикация модуля из PSGallery</span><span class="sxs-lookup"><span data-stu-id="ef061-172">Publishing a module from the PSGallery</span></span>

<span data-ttu-id="ef061-173">Чтобы опубликовать модуль из PSGallery в локальном репозитории PSRepository, вы можно использовать командлет Save-Package.</span><span class="sxs-lookup"><span data-stu-id="ef061-173">To publish a module from the PSGallery to your local PSRepository, you can use the 'Save-Package' cmdlet.</span></span>

- <span data-ttu-id="ef061-174">Укажите имя пакета.</span><span class="sxs-lookup"><span data-stu-id="ef061-174">Specify the Name of the Package</span></span>
- <span data-ttu-id="ef061-175">Укажите NuGet в качестве поставщика.</span><span class="sxs-lookup"><span data-stu-id="ef061-175">Specify 'NuGet' as the Provider</span></span>
- <span data-ttu-id="ef061-176">Укажите расположение PSGallery в качестве источника (https://www.powershellgallery.com/api/v2)).</span><span class="sxs-lookup"><span data-stu-id="ef061-176">Specify the PSGallery location as the source (https://www.powershellgallery.com/api/v2)</span></span>
- <span data-ttu-id="ef061-177">Укажите путь к вашему локальному репозиторию.</span><span class="sxs-lookup"><span data-stu-id="ef061-177">Specify the path to your local Repository</span></span>

<span data-ttu-id="ef061-178">Пример.</span><span class="sxs-lookup"><span data-stu-id="ef061-178">Example:</span></span>

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider NuGet -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

<span data-ttu-id="ef061-179">Если ваш локальный репозиторий PSRepository имеет веб-интерфейс, для него требуется дополнительный шаг, на котором выполняется публикация с помощью nuget.exe.</span><span class="sxs-lookup"><span data-stu-id="ef061-179">If your local PSRepository is web-based, it requires an additional step that uses nuget.exe to publish.</span></span>

<span data-ttu-id="ef061-180">См. документацию по использованию [nuget.exe][].</span><span class="sxs-lookup"><span data-stu-id="ef061-180">See the documentation for using [nuget.exe][].</span></span>

## <a name="installing-powershellget-on-a-disconnected-system"></a><span data-ttu-id="ef061-181">Установка PowerShellGet в отключенной системе</span><span class="sxs-lookup"><span data-stu-id="ef061-181">Installing PowerShellGet on a disconnected system</span></span>

<span data-ttu-id="ef061-182">Развертывание PowerShellGet затруднено в средах, где требуется отключение систем от Интернета.</span><span class="sxs-lookup"><span data-stu-id="ef061-182">Deploying PowerShellGet is difficult in environments that require systems to be disconnected from the internet.</span></span> <span data-ttu-id="ef061-183">PowerShellGet имеет процесс начальной загрузки, который устанавливает последнюю версию при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="ef061-183">PowerShellGet has a bootstrap process that installs the latest version the first time it's used.</span></span> <span data-ttu-id="ef061-184">Модуль OfflinePowerShellGetDeploy в коллекции PowerShell предоставляет командлеты, которые поддерживают этот процесс начальной загрузки.</span><span class="sxs-lookup"><span data-stu-id="ef061-184">The OfflinePowerShellGetDeploy module in the PowerShell Gallery provides cmdlets that support this bootstrap process.</span></span>

<span data-ttu-id="ef061-185">Чтобы выполнить начальную загрузку автономного развертывания, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="ef061-185">To bootstrap an offline deployment, you need to:</span></span>

- <span data-ttu-id="ef061-186">Скачайте и установите OfflinePowerShellGetDeploy в вашей подключенной к Интернету и отключенных системах.</span><span class="sxs-lookup"><span data-stu-id="ef061-186">Download and install the OfflinePowerShellGetDeploy your internet-connected system and your disconnected systems</span></span>
- <span data-ttu-id="ef061-187">Скачайте PowerShellGet и его зависимости на подключенную к Интернету систему с помощью командлета `Save-PowerShellGetForOffline`.</span><span class="sxs-lookup"><span data-stu-id="ef061-187">Download PowerShellGet and its dependencies on the internet-connected system using the `Save-PowerShellGetForOffline` cmdlet</span></span>
- <span data-ttu-id="ef061-188">Скопируйте PowerShellGet и его зависимости из подключенной к Интернету системы в отключенную систему.</span><span class="sxs-lookup"><span data-stu-id="ef061-188">Copy PowerShellGet and its dependencies from the internet-connected system to the disconnected system</span></span>
- <span data-ttu-id="ef061-189">Чтобы поместить PowerShellGet и его зависимости в соответствующие папки, используйте командлет `Install-PowerShellGetOffline` в отключенной системе.</span><span class="sxs-lookup"><span data-stu-id="ef061-189">Use the `Install-PowerShellGetOffline` on the disconnected system to place PowerShellGet and its dependencies into the proper folders</span></span>

<span data-ttu-id="ef061-190">Следующие команды используют `Save-PowerShellGetForOffline`, чтобы поместить все компоненты в папку `f:\OfflinePowerShellGet`.</span><span class="sxs-lookup"><span data-stu-id="ef061-190">The following commands use `Save-PowerShellGetForOffline` to put all the components into a folder `f:\OfflinePowerShellGet`</span></span>

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="ef061-191">На этом этапе необходимо сделать содержимое `F:\OfflinePowerShellGet` доступным для ваших отключенных систем.</span><span class="sxs-lookup"><span data-stu-id="ef061-191">At this point, you must make the contents of `F:\OfflinePowerShellGet` available to your disconnected systems.</span></span> <span data-ttu-id="ef061-192">Запустите командлет `Install-PowerShellGetOffline`, чтобы установить PowerShellGet в отключенной системе.</span><span class="sxs-lookup"><span data-stu-id="ef061-192">Run the `Install-PowerShellGetOffline` cmdlet to install PowerShellGet on the disconnected system.</span></span>

> [!NOTE]
> <span data-ttu-id="ef061-193">Важно, чтобы вы не запускали PowerShellGet в сеансе PowerShell перед выполнением этих команд.</span><span class="sxs-lookup"><span data-stu-id="ef061-193">It is important that you do not run PowerShellGet in the PowerShell session before running these commands.</span></span> <span data-ttu-id="ef061-194">После загрузки модуля PowerShellGet в сеанс компоненты невозможно обновить.</span><span class="sxs-lookup"><span data-stu-id="ef061-194">Once PowerShellGet is loaded into the session, the components cannot be updated.</span></span> <span data-ttu-id="ef061-195">Если вы по ошибке запустили PowerShellGet, закройте и перезапустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef061-195">If you do start PowerShellGet by mistake, exit and restart PowerShell.</span></span>

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="ef061-196">После выполнения этих команд вы сможете опубликовать модуль PowerShellGet в своем локальном репозитории.</span><span class="sxs-lookup"><span data-stu-id="ef061-196">After running these commands, you are ready to publish PowerShellGet to your local repository.</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey $nuGetApiKey
```

> [!IMPORTANT]
> <span data-ttu-id="ef061-197">Чтобы обеспечить безопасность, ключи API не следует жестко программировать в скриптах.</span><span class="sxs-lookup"><span data-stu-id="ef061-197">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="ef061-198">Используйте безопасную систему управления ключами.</span><span class="sxs-lookup"><span data-stu-id="ef061-198">Use a secure key management system.</span></span> <span data-ttu-id="ef061-199">При выполнении команды вручную ключи API не должны передаваться как обычный текст, чтобы избежать записи в журнал. Для безопасной передачи значения ключа API можно использовать командлет `Read-Host`.</span><span class="sxs-lookup"><span data-stu-id="ef061-199">When executing a command manually, API keys should not be passed as plain-text to avoid it being logged, the `Read-Host` cmdlet can be used to safely pass the value of the API key.</span></span>

```powershell
# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

## <a name="use-packaging-solutions-to-host-powershellget-repositories"></a><span data-ttu-id="ef061-200">Использование решений упаковки для размещения репозиториев PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="ef061-200">Use Packaging solutions to host PowerShellGet repositories</span></span>

<span data-ttu-id="ef061-201">Вы также можете использовать такие решения упаковки, как Azure Artifacts, для размещения частного или общедоступного репозитория PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="ef061-201">You can also use packaging solutions like Azure Artifacts to host a private or public PowerShellGet repository.</span></span> <span data-ttu-id="ef061-202">Дополнительные сведения и инструкции см. в [документации по Azure Artifacts](/azure/devops/artifacts/tutorials/private-powershell-library).</span><span class="sxs-lookup"><span data-stu-id="ef061-202">For more information and instructions, see the [Azure Artifacts documentation](/azure/devops/artifacts/tutorials/private-powershell-library).</span></span>

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[NuGet.Server]: /nuget/hosting-packages/nuget-server
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
