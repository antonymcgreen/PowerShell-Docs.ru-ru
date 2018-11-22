---
ms.date: 11/06/2018
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery,psget
title: Работа с локального PSRepositories
ms.openlocfilehash: 94824ea584c097838b24c6f2cd02407b6147a781
ms.sourcegitcommit: 91786b03704fbd2d185f674df0bc67faddfb6288
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619221"
---
# <a name="working-with-local-powershellget-repositories"></a><span data-ttu-id="d0129-103">Работа с локальными хранилищами PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="d0129-103">Working with local PowerShellGet Repositories</span></span>

<span data-ttu-id="d0129-104">Поддержка модуля PowerShellGet репозитории отличный от коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0129-104">The PowerShellGet module support repositories other than the PowerShell Gallery.</span></span>
<span data-ttu-id="d0129-105">Эти командлеты реализации следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="d0129-105">These cmdlets enable the following scenarios:</span></span>

- <span data-ttu-id="d0129-106">Поддерживает набор доверенных, предварительно проверенных модулей PowerShell для использования в вашей среде</span><span class="sxs-lookup"><span data-stu-id="d0129-106">Support a trusted, pre-validated set of PowerShell modules for use in your environment</span></span>
- <span data-ttu-id="d0129-107">Тестирование конвейера CI/CD, который создает модули PowerShell или сценариев</span><span class="sxs-lookup"><span data-stu-id="d0129-107">Testing a CI/CD pipeline that builds PowerShell modules or scripts</span></span>
- <span data-ttu-id="d0129-108">Доставлять сценариев и модулей PowerShell системы, для которых не удается получить доступ к Интернету</span><span class="sxs-lookup"><span data-stu-id="d0129-108">Deliver PowerShell scripts and modules to systems that can't access the internet</span></span>

<span data-ttu-id="d0129-109">В этой статье описывается настройка локального репозитория PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0129-109">This article describes how to set up a local PowerShell repository.</span></span> <span data-ttu-id="d0129-110">В статье также описаны [OfflinePowerShellGetDeploy][] модуль из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0129-110">The article also covers the [OfflinePowerShellGetDeploy][] module available from the PowerShell Gallery.</span></span> <span data-ttu-id="d0129-111">Этот модуль содержит командлеты, чтобы установить последнюю версию PowerShellGet в локальный репозиторий.</span><span class="sxs-lookup"><span data-stu-id="d0129-111">This module contains cmdlets to install the latest version of PowerShellGet into your local repository.</span></span>

## <a name="local-repository-types"></a><span data-ttu-id="d0129-112">Типы локального репозитория</span><span class="sxs-lookup"><span data-stu-id="d0129-112">Local repository types</span></span>

<span data-ttu-id="d0129-113">Существует два способа для создания локального PSRepository: NuGet server или файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="d0129-113">There are two ways to create a local PSRepository: NuGet server or file share.</span></span> <span data-ttu-id="d0129-114">Каждый тип имеет преимущества и недостатки:</span><span class="sxs-lookup"><span data-stu-id="d0129-114">Each type has advantages and disadvantages:</span></span>

<span data-ttu-id="d0129-115">Сервер NuGet</span><span class="sxs-lookup"><span data-stu-id="d0129-115">NuGet Server</span></span>

| <span data-ttu-id="d0129-116">Преимущества</span><span class="sxs-lookup"><span data-stu-id="d0129-116">Advantages</span></span>| <span data-ttu-id="d0129-117">Недостатки</span><span class="sxs-lookup"><span data-stu-id="d0129-117">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="d0129-118">Точно имитирует функциональность PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="d0129-118">Closely mimics PowerShellGallery functionality</span></span> | <span data-ttu-id="d0129-119">Многоуровневое приложение требует планирования операций и поддержка</span><span class="sxs-lookup"><span data-stu-id="d0129-119">Multi-tier app requires operations planning & support</span></span> |
| <span data-ttu-id="d0129-120">NuGet интегрируется с Visual Studio и другие средства</span><span class="sxs-lookup"><span data-stu-id="d0129-120">NuGet integrates with Visual Studio, other tools</span></span> | <span data-ttu-id="d0129-121">Модель проверки подлинности и контроля учетных записей NuGet</span><span class="sxs-lookup"><span data-stu-id="d0129-121">Authentication model and NuGet accounts management needed</span></span> |
| <span data-ttu-id="d0129-122">NuGet поддерживает метаданные в `.Nupkg` пакетов</span><span class="sxs-lookup"><span data-stu-id="d0129-122">NuGet supports metadata in `.Nupkg` packages</span></span> | <span data-ttu-id="d0129-123">Публикации требуется ключ API управление и обслуживание</span><span class="sxs-lookup"><span data-stu-id="d0129-123">Publishing requires API Key management & maintenance</span></span> |
| <span data-ttu-id="d0129-124">Предоставляет поиска, пакет администрирования и т. д.</span><span class="sxs-lookup"><span data-stu-id="d0129-124">Provides search, package administration, etc.</span></span> | |

<span data-ttu-id="d0129-125">Общая папка</span><span class="sxs-lookup"><span data-stu-id="d0129-125">File Share</span></span>

| <span data-ttu-id="d0129-126">Преимущества</span><span class="sxs-lookup"><span data-stu-id="d0129-126">Advantages</span></span>| <span data-ttu-id="d0129-127">Недостатки</span><span class="sxs-lookup"><span data-stu-id="d0129-127">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="d0129-128">Легко настроить, резервное копирование и поддерживать</span><span class="sxs-lookup"><span data-stu-id="d0129-128">Easy to set up, back up, and maintain</span></span> | <span data-ttu-id="d0129-129">Метаданные, используемые PowerShellGet недоступна</span><span class="sxs-lookup"><span data-stu-id="d0129-129">Metadata used by PowerShellGet isn't available</span></span> |
| <span data-ttu-id="d0129-130">Модель безопасности — разрешения пользователя в общей папке</span><span class="sxs-lookup"><span data-stu-id="d0129-130">Simple security model - user permissions on the share</span></span> | <span data-ttu-id="d0129-131">Ни один пользовательский Интерфейс за пределы базовый файловый ресурс</span><span class="sxs-lookup"><span data-stu-id="d0129-131">No UI beyond basic file share</span></span> |
| <span data-ttu-id="d0129-132">Без ограничений, таких как замена существующих элементов</span><span class="sxs-lookup"><span data-stu-id="d0129-132">No constraints such as replacing existing items</span></span> | <span data-ttu-id="d0129-133">Нет записи, от тех, кто обновляет новые и ограниченной безопасностью</span><span class="sxs-lookup"><span data-stu-id="d0129-133">Limited security and no recording of who updates what</span></span> |

<span data-ttu-id="d0129-134">PowerShellGet работает с типом и поддерживает поиск версии и установка зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d0129-134">PowerShellGet works with either type and supports locating versions and dependency installation.</span></span>
<span data-ttu-id="d0129-135">Тем не менее некоторые функции работают для коллекции PowerShell недоступны для базового NuGet серверов или общих папок.</span><span class="sxs-lookup"><span data-stu-id="d0129-135">However, some features that work for the PowerShell Gallery aren't available for base NuGet servers or file shares.</span></span>

- <span data-ttu-id="d0129-136">Все, что является пакетом - никакой разницы, сценарии, модули, ресурсы DSC и возможности ролей.</span><span class="sxs-lookup"><span data-stu-id="d0129-136">Everything is a package - no differentiation of scripts, modules, DSC resources, or role capabilities.</span></span>
- <span data-ttu-id="d0129-137">Файловые серверы общего ресурса не могут видеть метаданные пакета, включая теги.</span><span class="sxs-lookup"><span data-stu-id="d0129-137">File share servers can't see package metadata, including tags.</span></span>

## <a name="creating-a-local-repository"></a><span data-ttu-id="d0129-138">Создание локального репозитория</span><span class="sxs-lookup"><span data-stu-id="d0129-138">Creating a local repository</span></span>

<span data-ttu-id="d0129-139">В следующей статье перечислены шаги по настройке сервера NuGet.</span><span class="sxs-lookup"><span data-stu-id="d0129-139">The following article lists the steps for setting up your own NuGet Server.</span></span>

- <span data-ttu-id="d0129-140">[NuGet.Server][]</span><span class="sxs-lookup"><span data-stu-id="d0129-140">[NuGet.Server][]</span></span>

<span data-ttu-id="d0129-141">Следуйте инструкциям вплоть до добавления пакетов.</span><span class="sxs-lookup"><span data-stu-id="d0129-141">Follow the steps up to the point of adding packages.</span></span> <span data-ttu-id="d0129-142">Действия по [публикации пакета](#publishing-to-a-local-repository) рассматриваются далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d0129-142">The steps for [publishing a package](#publishing-to-a-local-repository) are covered later in this article.</span></span>

<span data-ttu-id="d0129-143">Для репозитория основе общих файлов убедитесь, что у пользователей есть разрешения на доступ к общей папке.</span><span class="sxs-lookup"><span data-stu-id="d0129-143">For a file share-based repository, make sure that your users have permissions to access the file share.</span></span>

## <a name="registering-a-local-repository"></a><span data-ttu-id="d0129-144">Регистрация локального репозитория</span><span class="sxs-lookup"><span data-stu-id="d0129-144">Registering a local repository</span></span>

<span data-ttu-id="d0129-145">Прежде чем можно будет использовать репозиторий, его необходимо зарегистрировать с помощью `Register-PSRepository` команды.</span><span class="sxs-lookup"><span data-stu-id="d0129-145">Before a repository can be used, it must be registered using the `Register-PSRepository` command.</span></span>
<span data-ttu-id="d0129-146">В приведенных ниже примерах **InstallationPolicy** присваивается *надежных*, на предположении, что вы доверяете ваш собственный репозиторий.</span><span class="sxs-lookup"><span data-stu-id="d0129-146">In the examples below, the **InstallationPolicy** is set to *Trusted*, on the assumption that you trust your own repository.</span></span>

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

<span data-ttu-id="d0129-147">Запишите разницу между порядок обработки двух команд **ScriptSourceLocation**.</span><span class="sxs-lookup"><span data-stu-id="d0129-147">Take note of the difference between how the two commands handle **ScriptSourceLocation**.</span></span> <span data-ttu-id="d0129-148">Для файла ресурса репозиториев на основе **SourceLocation** и **ScriptSourceLocation** должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="d0129-148">For a file share-based repositories, the **SourceLocation** and **ScriptSourceLocation** must match.</span></span> <span data-ttu-id="d0129-149">Для репозитория на основе веб технологий, они должны быть разными, поэтому в этом примере символ «/» добавляется **SourceLocation**.</span><span class="sxs-lookup"><span data-stu-id="d0129-149">For a web-based repository, they must be different, so in this example a trailing "/" is added to the **SourceLocation**.</span></span>

<span data-ttu-id="d0129-150">Если требуется только что созданный PSRepository быть репозитория по умолчанию, необходимо отменить регистрацию всех PSRepositories.</span><span class="sxs-lookup"><span data-stu-id="d0129-150">If you want the newly created PSRepository to be the default repository, you must unregister all other PSRepositories.</span></span> <span data-ttu-id="d0129-151">Например:</span><span class="sxs-lookup"><span data-stu-id="d0129-151">For example:</span></span>

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> <span data-ttu-id="d0129-152">Имя репозитория «PSGallery» зарезервирован для использования в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0129-152">The repository name 'PSGallery' is reserved for use by the PowerShell Gallery.</span></span> <span data-ttu-id="d0129-153">Вы можете отменить регистрацию PSGallery, но нельзя повторно использовать имя PSGallery для другого репозитория.</span><span class="sxs-lookup"><span data-stu-id="d0129-153">You can unregister PSGallery, but you cannot reuse the name PSGallery for any other repository.</span></span>

<span data-ttu-id="d0129-154">Если необходимо восстановить PSGallery, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0129-154">If you need to restore the PSGallery, run the following command:</span></span>

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a><span data-ttu-id="d0129-155">Публикации в локальном репозитории</span><span class="sxs-lookup"><span data-stu-id="d0129-155">Publishing to a local repository</span></span>

<span data-ttu-id="d0129-156">После регистрации локального PSRepository, можно опубликовать ваш локальный PSRepository.</span><span class="sxs-lookup"><span data-stu-id="d0129-156">Once you've registered the local PSRepository, you can publish to your local PSRepository.</span></span> <span data-ttu-id="d0129-157">Существует два основных сценария публикации: публикация собственных модулей и публикации модуля из PSGallery.</span><span class="sxs-lookup"><span data-stu-id="d0129-157">There are two main publishing scenarios: publishing your own module and publishing a module from the PSGallery.</span></span>

### <a name="publishing-a-module-you-authored"></a><span data-ttu-id="d0129-158">Для публикации модуля, созданные</span><span class="sxs-lookup"><span data-stu-id="d0129-158">Publishing a module you authored</span></span>

<span data-ttu-id="d0129-159">Используйте `Publish-Module` и `Publish-Script` для публикации модуля в вашей локальной PSRepository так же, как и для коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0129-159">Use `Publish-Module` and `Publish-Script` to publish your module to your local PSRepository the same way you do for the PowerShell Gallery.</span></span>

- <span data-ttu-id="d0129-160">Укажите расположение для кода</span><span class="sxs-lookup"><span data-stu-id="d0129-160">Specify the location for your code</span></span>
- <span data-ttu-id="d0129-161">Укажите ключ API</span><span class="sxs-lookup"><span data-stu-id="d0129-161">Supply an API key</span></span>
- <span data-ttu-id="d0129-162">Укажите имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="d0129-162">Specify the repository name.</span></span> <span data-ttu-id="d0129-163">Например: `-PSRepository LocalPSRepo`</span><span class="sxs-lookup"><span data-stu-id="d0129-163">For example, `-PSRepository LocalPSRepo`</span></span>

> [!NOTE]
> <span data-ttu-id="d0129-164">Необходимо создать учетную запись на сервере NuGet, а затем войдите в для создания и сохранения ключ API.</span><span class="sxs-lookup"><span data-stu-id="d0129-164">You must create an account in the NuGet server, then sign in to generate and save the API key.</span></span>
> <span data-ttu-id="d0129-165">Для файлового ресурса используйте любой непустой строкой для NuGetApiKey значения.</span><span class="sxs-lookup"><span data-stu-id="d0129-165">For a file share, use any non-blank string for the NuGetApiKey value.</span></span>

<span data-ttu-id="d0129-166">Примеры</span><span class="sxs-lookup"><span data-stu-id="d0129-166">Examples:</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> <span data-ttu-id="d0129-167">Чтобы обеспечить безопасность, ключи API не следует жестко заданное в сценарии.</span><span class="sxs-lookup"><span data-stu-id="d0129-167">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="d0129-168">Используйте систему безопасное управление ключами.</span><span class="sxs-lookup"><span data-stu-id="d0129-168">Use a secure key management system.</span></span>

### <a name="publishing-a-module-from-the-psgallery"></a><span data-ttu-id="d0129-169">Публикация модуля из PSGallery</span><span class="sxs-lookup"><span data-stu-id="d0129-169">Publishing a module from the PSGallery</span></span>

<span data-ttu-id="d0129-170">Чтобы опубликовать модуль из PSGallery к вашей локальной PSRepository, можно использовать командлет «Save-Package».</span><span class="sxs-lookup"><span data-stu-id="d0129-170">To publish a module from the PSGallery to your local PSRepository, you can use the 'Save-Package' cmdlet.</span></span>

- <span data-ttu-id="d0129-171">Укажите имя пакета</span><span class="sxs-lookup"><span data-stu-id="d0129-171">Specify the Name of the Package</span></span>
- <span data-ttu-id="d0129-172">Укажите «NuGet» в качестве поставщика</span><span class="sxs-lookup"><span data-stu-id="d0129-172">Specify 'NuGet' as the Provider</span></span>
- <span data-ttu-id="d0129-173">Укажите расположение PSGallery в качестве источника)https://www.powershellgallery.com/api/v2)</span><span class="sxs-lookup"><span data-stu-id="d0129-173">Specify the PSGallery location as the source (https://www.powershellgallery.com/api/v2)</span></span>
- <span data-ttu-id="d0129-174">Укажите путь к локального репозитория</span><span class="sxs-lookup"><span data-stu-id="d0129-174">Specify the path to your local Repository</span></span>

<span data-ttu-id="d0129-175">Пример:</span><span class="sxs-lookup"><span data-stu-id="d0129-175">Example:</span></span>

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider Nuget -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

<span data-ttu-id="d0129-176">Если ваш локальный PSRepository веб интерфейсом, то требуется дополнительный шаг, который использует nuget.exe для публикации.</span><span class="sxs-lookup"><span data-stu-id="d0129-176">If your local PSRepository is web-based, it requires an additional step that uses nuget.exe to publish.</span></span>

<span data-ttu-id="d0129-177">См. в документации по использованию [nuget.exe][].</span><span class="sxs-lookup"><span data-stu-id="d0129-177">See the documentation for using [nuget.exe][].</span></span>

## <a name="installing-powershellget-on-a-disconnected-system"></a><span data-ttu-id="d0129-178">Установка PowerShellGet в отключенной системе</span><span class="sxs-lookup"><span data-stu-id="d0129-178">Installing PowerShellGet on a disconnected system</span></span>

<span data-ttu-id="d0129-179">Развертывание PowerShellGet сложно в средах, требующих систем, чтобы быть отключен от Интернета.</span><span class="sxs-lookup"><span data-stu-id="d0129-179">Deploying PowerShellGet is difficult in environments that require systems to be disconnected from the internet.</span></span> <span data-ttu-id="d0129-180">С помощью PowerShellGet процесс начальной загрузки, который устанавливает последнюю версию при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="d0129-180">PowerShellGet has a bootstrap process that installs the latest version the first time it's used.</span></span> <span data-ttu-id="d0129-181">Модуль OfflinePowerShellGetDeploy в коллекции PowerShell предоставляет командлеты, поддерживающие этот процесс начальной загрузки.</span><span class="sxs-lookup"><span data-stu-id="d0129-181">The OfflinePowerShellGetDeploy module in the PowerShell Gallery provides cmdlets that support this bootstrap process.</span></span>

<span data-ttu-id="d0129-182">Чтобы выполнить начальную загрузку развертывания в автономном режиме, вам потребуется:</span><span class="sxs-lookup"><span data-stu-id="d0129-182">To bootstrap an offline deployment, you need to:</span></span>

- <span data-ttu-id="d0129-183">Скачайте и установите системы OfflinePowerShellGetDeploy вашей подключенной к Интернету и отключенных систем</span><span class="sxs-lookup"><span data-stu-id="d0129-183">Download and install the OfflinePowerShellGetDeploy your internet-connected system and your disconnected systems</span></span>
- <span data-ttu-id="d0129-184">Скачайте PowerShellGet и его зависимостей в системе, подключенной к Интернету с помощью `Save-PowerShellGetForOffline` командлета</span><span class="sxs-lookup"><span data-stu-id="d0129-184">Download PowerShellGet and its dependencies on the internet-connected system using the `Save-PowerShellGetForOffline` cmdlet</span></span>
- <span data-ttu-id="d0129-185">Скопируйте PowerShellGet и его зависимости из системы, подключенной к Интернету в отключенной системе</span><span class="sxs-lookup"><span data-stu-id="d0129-185">Copy PowerShellGet and its dependencies from the internet-connected system to the disconnected system</span></span>
- <span data-ttu-id="d0129-186">Используйте `Install-PowerShellGetOffline` в отключенной системе, чтобы поместить PowerShellGet и его зависимости в нужные папки</span><span class="sxs-lookup"><span data-stu-id="d0129-186">Use the `Install-PowerShellGetOffline` on the disconnected system to place PowerShellGet and its dependencies into the proper folders</span></span>

<span data-ttu-id="d0129-187">Следующие команды используют `Save-PowerShellGetForOffline` для размещения всех компонентов в папку `f:\OfflinePowerShellGet`</span><span class="sxs-lookup"><span data-stu-id="d0129-187">The following commands use `Save-PowerShellGetForOffline` to put all the components into a folder `f:\OfflinePowerShellGet`</span></span>

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="d0129-188">На этом этапе необходимо сделать содержимое `F:\OfflinePowerShellGet` для отключенных систем.</span><span class="sxs-lookup"><span data-stu-id="d0129-188">At this point, you must make the contents of `F:\OfflinePowerShellGet` available to your disconnected systems.</span></span> <span data-ttu-id="d0129-189">Запустите `Install-PowerShellGetOffline` командлет, чтобы установить PowerShellGet в отключенной системе.</span><span class="sxs-lookup"><span data-stu-id="d0129-189">Run the `Install-PowerShellGetOffline` cmdlet to install PowerShellGet on the disconnected system.</span></span>

> [!NOTE]
> <span data-ttu-id="d0129-190">Очень важно, что не выполнять PowerShellGet в сеансе PowerShell перед выполнением этих команд.</span><span class="sxs-lookup"><span data-stu-id="d0129-190">It is important that you do not run PowerShellGet in the PowerShell session before running these commands.</span></span> <span data-ttu-id="d0129-191">После загрузки PowerShellGet в сеанс не удается обновить компоненты.</span><span class="sxs-lookup"><span data-stu-id="d0129-191">Once PowerShellGet is loaded into the session, the components cannot be updated.</span></span> <span data-ttu-id="d0129-192">При запуске PowerShellGet по ошибке, закройте и перезапустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0129-192">If you do start PowerShellGet by mistake, exit and restart PowerShell.</span></span>

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="d0129-193">После выполнения этих команд, все готово для публикации PowerShellGet в локальном репозитории.</span><span class="sxs-lookup"><span data-stu-id="d0129-193">After running these commands, you are ready to publish PowerShellGet to your local repository.</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> <span data-ttu-id="d0129-194">Чтобы обеспечить безопасность, ключи API не следует жестко заданное в сценарии.</span><span class="sxs-lookup"><span data-stu-id="d0129-194">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="d0129-195">Используйте систему безопасное управление ключами.</span><span class="sxs-lookup"><span data-stu-id="d0129-195">Use a secure key management system.</span></span>

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[NuGet.exe]: /nuget/tools/nuget-exe-cli-reference
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
