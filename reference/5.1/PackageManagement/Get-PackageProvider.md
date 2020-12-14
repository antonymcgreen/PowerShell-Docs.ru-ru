---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 66a6bfeda557894e224753018ff9087de9887cc7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892862"
---
# <span data-ttu-id="8f249-103">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8f249-103">Get-PackageProvider</span></span>

## <span data-ttu-id="8f249-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8f249-104">SYNOPSIS</span></span>
<span data-ttu-id="8f249-105">Возвращает список поставщиков пакетов, подключенных к системе управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="8f249-105">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="8f249-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f249-106">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="8f249-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f249-107">DESCRIPTION</span></span>
<span data-ttu-id="8f249-108">Командлет **Get-PackageProvider** возвращает список поставщиков пакетов, подключенных к системе управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="8f249-108">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="8f249-109">К ним относятся, например, PSModule, NuGet и Chocolatey.</span><span class="sxs-lookup"><span data-stu-id="8f249-109">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="8f249-110">Результаты можно отфильтровать на основе имен (полных или их части) поставщиков.</span><span class="sxs-lookup"><span data-stu-id="8f249-110">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="8f249-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="8f249-111">EXAMPLES</span></span>

### <span data-ttu-id="8f249-112">Пример 1. Получение всех загруженных в настоящее время поставщиков пакетов</span><span class="sxs-lookup"><span data-stu-id="8f249-112">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="8f249-113">Эта команда возвращает список всех поставщиков пакетов, загруженных в настоящий момент на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8f249-113">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="8f249-114">Пример 2. Получение списка всех доступных поставщиков пакетов</span><span class="sxs-lookup"><span data-stu-id="8f249-114">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="8f249-115">Эта команда возвращает список всех поставщиков пакетов, доступных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8f249-115">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="8f249-116">Пример 3. Динамическое получение поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="8f249-116">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="8f249-117">Эта команда автоматически устанавливает поставщик Chocolatey, если он еще не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8f249-117">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="8f249-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f249-118">PARAMETERS</span></span>

### <span data-ttu-id="8f249-119">-Force</span><span class="sxs-lookup"><span data-stu-id="8f249-119">-Force</span></span>
<span data-ttu-id="8f249-120">Указывает, что этот командлет принудительно выполняет все доступные для этого командлета действия.</span><span class="sxs-lookup"><span data-stu-id="8f249-120">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="8f249-121">Это означает, что в командлете **Get-PackageProvider** параметр *Force* действует так же, как и параметр *ForceBootstrap*.</span><span class="sxs-lookup"><span data-stu-id="8f249-121">In **Get-PackageProvider**, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="8f249-122">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="8f249-122">-ForceBootstrap</span></span>
<span data-ttu-id="8f249-123">Указывает, что этот командлет заставляет систему управления пакетами автоматически установить поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="8f249-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="8f249-124">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="8f249-124">-ListAvailable</span></span>
<span data-ttu-id="8f249-125">Получает все установленные поставщики.</span><span class="sxs-lookup"><span data-stu-id="8f249-125">Gets all installed providers.</span></span>
<span data-ttu-id="8f249-126">**Get-PackageProvider** Получает поставщик в путях, указанных в переменной среды **PSModulePath** , а также в папках сборки поставщика пакетов:</span><span class="sxs-lookup"><span data-stu-id="8f249-126">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="8f249-127">**$env:P Рограмфилес\паккажеманажемент\провидерассемблиес \* \* \* \* $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span><span class="sxs-lookup"><span data-stu-id="8f249-127">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="8f249-128">Без этого параметра командлет **Get-PackageProvider** получает только поставщики, загруженные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="8f249-128">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="8f249-129">-Name</span><span class="sxs-lookup"><span data-stu-id="8f249-129">-Name</span></span>
<span data-ttu-id="8f249-130">Задает одно или несколько имен поставщиков или их часть.</span><span class="sxs-lookup"><span data-stu-id="8f249-130">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="8f249-131">Имена нескольких поставщиков нужно разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="8f249-131">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="8f249-132">Допустимые значения: имена установленных поставщиков пакетов, поставки PackageManagement с набором поставщиков по умолчанию, в том числе поставщики **PSModule** и **MSI**.</span><span class="sxs-lookup"><span data-stu-id="8f249-132">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

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

### <span data-ttu-id="8f249-133">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8f249-133">CommonParameters</span></span>
<span data-ttu-id="8f249-134">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f249-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f249-135">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f249-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f249-136">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8f249-136">INPUTS</span></span>

## <span data-ttu-id="8f249-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8f249-137">OUTPUTS</span></span>

### <span data-ttu-id="8f249-138">PackageProvider[]</span><span class="sxs-lookup"><span data-stu-id="8f249-138">PackageProvider[]</span></span>

## <span data-ttu-id="8f249-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8f249-139">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f249-140">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="8f249-140">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="8f249-141">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="8f249-141">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="8f249-142">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="8f249-142">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="8f249-143">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f249-143">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="8f249-144">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8f249-144">RELATED LINKS</span></span>

[<span data-ttu-id="8f249-145">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="8f249-145">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="8f249-146">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8f249-146">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="8f249-147">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8f249-147">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="8f249-148">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8f249-148">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
