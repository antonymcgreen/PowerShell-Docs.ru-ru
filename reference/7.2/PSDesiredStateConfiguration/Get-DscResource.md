---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: dbc036562da0172dc4406f169891d2cd1c5e4098
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602863"
---
# <span data-ttu-id="10b63-102">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="10b63-102">Get-DscResource</span></span>

## <span data-ttu-id="10b63-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="10b63-103">SYNOPSIS</span></span>
<span data-ttu-id="10b63-104">Получает ресурсы настройки требуемого состояния (DSC), которые имеются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="10b63-104">Gets Desired State Configuration (DSC) resources present on the computer.</span></span>

## <span data-ttu-id="10b63-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10b63-105">SYNTAX</span></span>

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## <span data-ttu-id="10b63-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10b63-106">DESCRIPTION</span></span>

<span data-ttu-id="10b63-107">`Get-DscResource`Командлет извлекает ресурсы DSC PowerShell, имеющиеся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="10b63-107">The `Get-DscResource` cmdlet retrieves the PowerShell DSC resources present on the computer.</span></span> <span data-ttu-id="10b63-108">Этот командлет обнаруживает только ресурсы, установленные в PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="10b63-108">This cmdlet discovers only the resources installed in the PSModulePath.</span></span> <span data-ttu-id="10b63-109">В нем отображаются сведения о встроенных и пользовательских поставщиках, создаваемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="10b63-109">It shows the details about built-in and custom providers, which are created by the user.</span></span> <span data-ttu-id="10b63-110">Этот командлет также отображает сведения о составных ресурсах, которые являются другими конфигурациями, упакованными в модуль или созданными во время выполнения в сеансе.</span><span class="sxs-lookup"><span data-stu-id="10b63-110">This cmdlet also shows details about composite resources, which are other configurations that are packaged as module or created at run time in the session.</span></span>

## <span data-ttu-id="10b63-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="10b63-111">EXAMPLES</span></span>

### <span data-ttu-id="10b63-112">Пример 1. получение всех ресурсов на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="10b63-112">Example 1: Get all resources on the local computer</span></span>

```powershell
Get-DscResource
```

<span data-ttu-id="10b63-113">Эта команда возвращает все ресурсы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="10b63-113">This command gets all the resources on the local computer.</span></span>

### <span data-ttu-id="10b63-114">Пример 2. Получение ресурса путем указания имени</span><span class="sxs-lookup"><span data-stu-id="10b63-114">Example 2: Get a resource by specifying the name</span></span>

```powershell
Get-DscResource -Name "WindowsFeature"
```

<span data-ttu-id="10b63-115">Эта команда возвращает ресурс WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="10b63-115">This command gets the WindowsFeature resource.</span></span>

### <span data-ttu-id="10b63-116">Пример 3. получение всех ресурсов из модуля</span><span class="sxs-lookup"><span data-stu-id="10b63-116">Example 3: Get all the resources from a module</span></span>

```powershell
Get-DscResource -Module "xHyper-V"
```

<span data-ttu-id="10b63-117">Эта команда получает все ресурсы из модуля Ксхипер-V.</span><span class="sxs-lookup"><span data-stu-id="10b63-117">This command gets all the resources from the xHyper-V module.</span></span>

### <span data-ttu-id="10b63-118">Пример 4. Получение ресурса с помощью подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="10b63-118">Example 4: Get a resource by using wildcard characters</span></span>

```powershell
Get-DscResource -Name P*,r*
```

<span data-ttu-id="10b63-119">Эта команда возвращает все ресурсы, соответствующие шаблону с подстановочным знаком, заданному параметром **Name** .</span><span class="sxs-lookup"><span data-stu-id="10b63-119">This command gets all resources that match the wildcard pattern specified by the **Name** parameter.</span></span>

### <span data-ttu-id="10b63-120">Пример 5. получение синтаксиса ресурсов</span><span class="sxs-lookup"><span data-stu-id="10b63-120">Example 5: Get a resource syntax</span></span>

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

<span data-ttu-id="10b63-121">Эта команда возвращает ресурс WindowsFeature и отображает синтаксис для ресурса.</span><span class="sxs-lookup"><span data-stu-id="10b63-121">This command gets the WindowsFeature resource, and shows the syntax for the resource.</span></span>

### <span data-ttu-id="10b63-122">Пример 6. получение всех свойств ресурса</span><span class="sxs-lookup"><span data-stu-id="10b63-122">Example 6: Get all the properties for a resource</span></span>

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

<span data-ttu-id="10b63-123">Эта команда возвращает  ресурс пользователя, а затем использует оператор конвейера для возврата всех свойств для ресурса пользователя.</span><span class="sxs-lookup"><span data-stu-id="10b63-123">This command gets the User resource, and then uses the pipeline operator to return all the properties for the User resource.</span></span>

### <span data-ttu-id="10b63-124">Пример 7. получение всех ресурсов из указанного модуля с указанной версией</span><span class="sxs-lookup"><span data-stu-id="10b63-124">Example 7: Get all the resources from a specified module with a specified version</span></span>

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

<span data-ttu-id="10b63-125">Эта команда получает все ресурсы из модуля Ксхипер-V с версией 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="10b63-125">This command gets all the resources from xHyper-V module with version 3.0.0.0.</span></span>

## <span data-ttu-id="10b63-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10b63-126">PARAMETERS</span></span>

### <span data-ttu-id="10b63-127">-Module</span><span class="sxs-lookup"><span data-stu-id="10b63-127">-Module</span></span>

<span data-ttu-id="10b63-128">Указывает имя или полное имя модуля, для которого необходимо просмотреть ресурс DSC.</span><span class="sxs-lookup"><span data-stu-id="10b63-128">Specifies the name or fully qualified name of the module for which to view the DSC resource.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="10b63-129">-Name</span><span class="sxs-lookup"><span data-stu-id="10b63-129">-Name</span></span>

<span data-ttu-id="10b63-130">Указывает массив имен ресурса DSC для просмотра.</span><span class="sxs-lookup"><span data-stu-id="10b63-130">Specifies an array of names of the DSC resource to view.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="10b63-131">-Syntax</span><span class="sxs-lookup"><span data-stu-id="10b63-131">-Syntax</span></span>

<span data-ttu-id="10b63-132">Указывает, что командлет возвращает представление синтаксиса для указанных ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="10b63-132">Indicates that the cmdlet returns the syntax view of the specified DSC resources.</span></span> <span data-ttu-id="10b63-133">Возвращаемый синтаксис показывает, как использовать ресурсы в скрипте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10b63-133">The returned syntax shows how to use the resources in a PowerShell script.</span></span>

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

### <span data-ttu-id="10b63-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="10b63-134">CommonParameters</span></span>

<span data-ttu-id="10b63-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="10b63-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10b63-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="10b63-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10b63-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="10b63-137">INPUTS</span></span>

### <span data-ttu-id="10b63-138">System.String[]</span><span class="sxs-lookup"><span data-stu-id="10b63-138">System.String[]</span></span>

### <span data-ttu-id="10b63-139">System.Object</span><span class="sxs-lookup"><span data-stu-id="10b63-139">System.Object</span></span>

## <span data-ttu-id="10b63-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="10b63-140">OUTPUTS</span></span>

### <span data-ttu-id="10b63-141">Microsoft. PowerShell. Десиредстатеконфигуратион. Дскресаурцеинфо []</span><span class="sxs-lookup"><span data-stu-id="10b63-141">Microsoft.PowerShell.DesiredStateConfiguration.DscResourceInfo[]</span></span>

### <span data-ttu-id="10b63-142">string[]</span><span class="sxs-lookup"><span data-stu-id="10b63-142">string[]</span></span>

## <span data-ttu-id="10b63-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="10b63-143">NOTES</span></span>

## <span data-ttu-id="10b63-144">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="10b63-144">RELATED LINKS</span></span>

[<span data-ttu-id="10b63-145">Общие сведения о настройке требуемого состояния PowerShell</span><span class="sxs-lookup"><span data-stu-id="10b63-145">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="10b63-146">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="10b63-146">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)

