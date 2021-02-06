---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 6c19d1cbc7b7e4dc37e24c466f83efae688f3cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602856"
---
# <span data-ttu-id="1a87b-102">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="1a87b-102">Import-PackageProvider</span></span>

## <span data-ttu-id="1a87b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1a87b-103">SYNOPSIS</span></span>
<span data-ttu-id="1a87b-104">Добавляет поставщики пакетов Управление пакетами в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="1a87b-104">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="1a87b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a87b-105">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="1a87b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a87b-106">DESCRIPTION</span></span>

<span data-ttu-id="1a87b-107">`Import-PackageProvider`Командлет добавляет один или несколько поставщиков пакетов в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="1a87b-107">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="1a87b-108">Импортируемый поставщик должен быть установлен на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a87b-108">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="1a87b-109">Чтобы получить список доступных поставщиков, выполните команду `Get-PackageProvider -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="1a87b-109">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="1a87b-110">Обратите внимание, что имя поставщика пакета может отличаться от имени модуля.</span><span class="sxs-lookup"><span data-stu-id="1a87b-110">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="1a87b-111">Из соображений безопасности **PackageManagement** требует, чтобы поставщики на основе C# содержали `provider.manifest` .</span><span class="sxs-lookup"><span data-stu-id="1a87b-111">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="1a87b-112">Дополнительные сведения о создании поставщика с `provider.manifest` внедренным см. в разделе `.csproj` файлы проекта в [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .</span><span class="sxs-lookup"><span data-stu-id="1a87b-112">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="1a87b-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="1a87b-113">EXAMPLES</span></span>

### <span data-ttu-id="1a87b-114">Пример 1. Импорт поставщика пакетов с локального компьютера</span><span class="sxs-lookup"><span data-stu-id="1a87b-114">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="1a87b-115">Эта команда импортирует поставщик NuGet после установки на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a87b-115">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="1a87b-116">Пример 2. импорт определенной версии поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="1a87b-116">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="1a87b-117">Эта команда находит, устанавливает и импортирует определенную версию поставщика пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="1a87b-117">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="1a87b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a87b-118">PARAMETERS</span></span>

### <span data-ttu-id="1a87b-119">-Force</span><span class="sxs-lookup"><span data-stu-id="1a87b-119">-Force</span></span>

<span data-ttu-id="1a87b-120">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="1a87b-120">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="1a87b-121">Повторно импортирует поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="1a87b-121">Re-imports a package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a87b-122">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="1a87b-122">-ForceBootstrap</span></span>

<span data-ttu-id="1a87b-123">Указывает, что этот командлет заставляет систему управления пакетами автоматически установить поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="1a87b-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a87b-124">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="1a87b-124">-MaximumVersion</span></span>

<span data-ttu-id="1a87b-125">Указывает максимально допустимую версию поставщика пакета, который требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="1a87b-125">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="1a87b-126">Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию поставщика.</span><span class="sxs-lookup"><span data-stu-id="1a87b-126">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a87b-127">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1a87b-127">-MinimumVersion</span></span>

<span data-ttu-id="1a87b-128">Указывает минимально допустимую версию поставщика пакета, который требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="1a87b-128">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="1a87b-129">Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию пакета, которая также соответствует любой максимальной версии, указанной с помощью параметра *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="1a87b-129">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a87b-130">-Name</span><span class="sxs-lookup"><span data-stu-id="1a87b-130">-Name</span></span>

<span data-ttu-id="1a87b-131">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="1a87b-131">Specifies one or more package provider names.</span></span> <span data-ttu-id="1a87b-132">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="1a87b-132">Wildcards are not permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a87b-133">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="1a87b-133">-RequiredVersion</span></span>

<span data-ttu-id="1a87b-134">Указывает точную версию поставщика пакета, который требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="1a87b-134">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="1a87b-135">Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию поставщика, которая также соответствует максимальной версии, указанной в параметре **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="1a87b-135">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a87b-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1a87b-136">CommonParameters</span></span>

<span data-ttu-id="1a87b-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1a87b-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a87b-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1a87b-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a87b-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1a87b-139">INPUTS</span></span>

### <span data-ttu-id="1a87b-140">Microsoft. PackageManagement. Реализация. PackageProvider</span><span class="sxs-lookup"><span data-stu-id="1a87b-140">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="1a87b-141">Объект **PackageProvider** , возвращаемый, можно передать `Get-PackageProvider` в `Import-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="1a87b-141">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="1a87b-142">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1a87b-142">OUTPUTS</span></span>

## <span data-ttu-id="1a87b-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1a87b-143">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a87b-144">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="1a87b-144">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="1a87b-145">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="1a87b-145">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="1a87b-146">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1a87b-146">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="1a87b-147">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a87b-147">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="1a87b-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1a87b-148">RELATED LINKS</span></span>

[<span data-ttu-id="1a87b-149">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="1a87b-149">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="1a87b-150">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="1a87b-150">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="1a87b-151">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="1a87b-151">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="1a87b-152">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="1a87b-152">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="1a87b-153">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="1a87b-153">Get-PackageProvider</span></span>](Get-PackageProvider.md)
