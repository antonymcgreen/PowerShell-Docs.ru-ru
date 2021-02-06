---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: fd8325f1a68755ee1b5c05719a04e71b22a7e9fd
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601488"
---
# <span data-ttu-id="18894-102">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="18894-102">Get-PackageProvider</span></span>

## <span data-ttu-id="18894-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="18894-103">SYNOPSIS</span></span>
<span data-ttu-id="18894-104">Возвращает список поставщиков пакетов, подключенных к системе управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="18894-104">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="18894-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="18894-105">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="18894-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="18894-106">DESCRIPTION</span></span>

<span data-ttu-id="18894-107">Командлет **Get-PackageProvider** возвращает список поставщиков пакетов, подключенных к системе управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="18894-107">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="18894-108">К ним относятся, например, PSModule, NuGet и Chocolatey.</span><span class="sxs-lookup"><span data-stu-id="18894-108">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="18894-109">Результаты можно отфильтровать на основе имен (полных или их части) поставщиков.</span><span class="sxs-lookup"><span data-stu-id="18894-109">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="18894-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="18894-110">EXAMPLES</span></span>

### <span data-ttu-id="18894-111">Пример 1. Получение всех загруженных в настоящее время поставщиков пакетов</span><span class="sxs-lookup"><span data-stu-id="18894-111">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="18894-112">Эта команда возвращает список всех поставщиков пакетов, загруженных в настоящий момент на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="18894-112">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="18894-113">Пример 2. Получение списка всех доступных поставщиков пакетов</span><span class="sxs-lookup"><span data-stu-id="18894-113">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="18894-114">Эта команда возвращает список всех поставщиков пакетов, доступных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="18894-114">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="18894-115">Пример 3. Динамическое получение поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="18894-115">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="18894-116">Эта команда автоматически устанавливает поставщик Chocolatey, если он еще не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="18894-116">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="18894-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="18894-117">PARAMETERS</span></span>

### <span data-ttu-id="18894-118">-Force</span><span class="sxs-lookup"><span data-stu-id="18894-118">-Force</span></span>

<span data-ttu-id="18894-119">Указывает, что этот командлет принудительно выполняет все доступные для этого командлета действия.</span><span class="sxs-lookup"><span data-stu-id="18894-119">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="18894-120">Это означает, что в командлете **Get-PackageProvider** параметр *Force* действует так же, как и параметр *ForceBootstrap*.</span><span class="sxs-lookup"><span data-stu-id="18894-120">In **Get-PackageProvider**, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="18894-121">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="18894-121">-ForceBootstrap</span></span>

<span data-ttu-id="18894-122">Указывает, что этот командлет заставляет систему управления пакетами автоматически установить поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="18894-122">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="18894-123">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="18894-123">-ListAvailable</span></span>

<span data-ttu-id="18894-124">Получает все установленные поставщики.</span><span class="sxs-lookup"><span data-stu-id="18894-124">Gets all installed providers.</span></span>
<span data-ttu-id="18894-125">**Get-PackageProvider** Получает поставщик в путях, указанных в переменной среды **PSModulePath** , а также в папках сборки поставщика пакетов:</span><span class="sxs-lookup"><span data-stu-id="18894-125">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="18894-126">**$env:P Рограмфилес\паккажеманажемент\провидерассемблиес \* \* \* \* $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span><span class="sxs-lookup"><span data-stu-id="18894-126">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="18894-127">Без этого параметра командлет **Get-PackageProvider** получает только поставщики, загруженные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="18894-127">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="18894-128">-Name</span><span class="sxs-lookup"><span data-stu-id="18894-128">-Name</span></span>

<span data-ttu-id="18894-129">Задает одно или несколько имен поставщиков или их часть.</span><span class="sxs-lookup"><span data-stu-id="18894-129">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="18894-130">Имена нескольких поставщиков нужно разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="18894-130">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="18894-131">Допустимые значения: имена установленных поставщиков пакетов, поставки PackageManagement с набором поставщиков по умолчанию, в том числе поставщики **PSModule** и **MSI**.</span><span class="sxs-lookup"><span data-stu-id="18894-131">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18894-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="18894-132">CommonParameters</span></span>

<span data-ttu-id="18894-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="18894-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="18894-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="18894-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="18894-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="18894-135">INPUTS</span></span>

## <span data-ttu-id="18894-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="18894-136">OUTPUTS</span></span>

### <span data-ttu-id="18894-137">PackageProvider[]</span><span class="sxs-lookup"><span data-stu-id="18894-137">PackageProvider[]</span></span>

## <span data-ttu-id="18894-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="18894-138">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18894-139">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="18894-139">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="18894-140">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="18894-140">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="18894-141">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="18894-141">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="18894-142">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18894-142">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="18894-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="18894-143">RELATED LINKS</span></span>

[<span data-ttu-id="18894-144">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="18894-144">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="18894-145">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="18894-145">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="18894-146">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="18894-146">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="18894-147">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="18894-147">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
