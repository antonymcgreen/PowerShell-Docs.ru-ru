---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: d73d8d6a30e6b7c08b5a0b7988ea2327be34002a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228321"
---
# <span data-ttu-id="2ae99-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="2ae99-103">Invoke-DscResource</span></span>

## <span data-ttu-id="2ae99-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2ae99-104">SYNOPSIS</span></span>
<span data-ttu-id="2ae99-105">Выполняет метод указанного ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="2ae99-105">Runs a method of a specified DSC resource.</span></span>

## <span data-ttu-id="2ae99-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ae99-106">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [-Method] <String> -ModuleName <ModuleSpecification> -Property <Hashtable>
 [<CommonParameters>]
```

## <span data-ttu-id="2ae99-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ae99-107">DESCRIPTION</span></span>
<span data-ttu-id="2ae99-108">Командлет **Invoke-DscResource** запускает метод указанного ресурса настройки требуемого состояния Windows POWERSHELL (DSC).</span><span class="sxs-lookup"><span data-stu-id="2ae99-108">The **Invoke-DscResource** cmdlet runs a method of a specified Windows PowerShell Desired State Configuration (DSC) resource.</span></span>
<span data-ttu-id="2ae99-109">Перед запуском этого командлета задайте для параметра режим обновления локального Configuration Manager (LCM) значение отключено.</span><span class="sxs-lookup"><span data-stu-id="2ae99-109">Before you run this cmdlet, set the refresh mode of the Local Configuration Manager (LCM) to Disabled.</span></span>

<span data-ttu-id="2ae99-110">Этот командлет вызывает ресурс DSC напрямую, не создавая документ конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2ae99-110">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span>
<span data-ttu-id="2ae99-111">С помощью этого командлета продукты управления конфигурацией могут управлять Windows с помощью ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="2ae99-111">Using this cmdlet, configuration management products can manage windows by using DSC resources.</span></span>
<span data-ttu-id="2ae99-112">Этот командлет также позволяет выполнять отладку ресурсов при выполнении модуля DSC или LCM с включенной отладкой.</span><span class="sxs-lookup"><span data-stu-id="2ae99-112">This cmdlet also enables debugging of resources when the DSC engine or LCM is running with debugging enabled.</span></span>

## <span data-ttu-id="2ae99-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="2ae99-113">EXAMPLES</span></span>

### <span data-ttu-id="2ae99-114">Пример 1. вызов метода Set ресурса путем указания его обязательных свойств</span><span class="sxs-lookup"><span data-stu-id="2ae99-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

```
PS C:\> Invoke-DscResource -Name Log -Method Set -Property @{Message = 'Hello World'} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="2ae99-115">Эта команда вызывает метод **Set** ресурса с именем log и задает для него свойство **Message** .</span><span class="sxs-lookup"><span data-stu-id="2ae99-115">This command invokes the **Set** method of a resource named Log and specifies a **Message** property for it.</span></span>

### <span data-ttu-id="2ae99-116">Пример 2. вызов метода теста ресурса для указанного модуля</span><span class="sxs-lookup"><span data-stu-id="2ae99-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

```
PS C:\> Invoke-DscResource -Name WindowsProcess -Method Test -Property @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="2ae99-117">Эта команда вызывает метод **теста** ресурса с именем ресурс windowsprocess, который находится в модуле с именем PSDesiredStateConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2ae99-117">This command invokes the **Test** method of a resource named WindowsProcess, which is in the module named PSDesiredStateConfiguration.</span></span>

## <span data-ttu-id="2ae99-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ae99-118">PARAMETERS</span></span>

### <span data-ttu-id="2ae99-119">-Method</span><span class="sxs-lookup"><span data-stu-id="2ae99-119">-Method</span></span>
<span data-ttu-id="2ae99-120">Указывает метод ресурса, который вызывает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="2ae99-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="2ae99-121">Допустимые значения для этого параметра: Get, Set и Test.</span><span class="sxs-lookup"><span data-stu-id="2ae99-121">The acceptable values for this parameter are: Get, Set, and Test.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ae99-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="2ae99-122">-ModuleName</span></span>
<span data-ttu-id="2ae99-123">Указывает имя модуля, из которого этот командлет вызывает указанный ресурс.</span><span class="sxs-lookup"><span data-stu-id="2ae99-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ae99-124">-Name</span><span class="sxs-lookup"><span data-stu-id="2ae99-124">-Name</span></span>
<span data-ttu-id="2ae99-125">Указывает имя запускаемого ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="2ae99-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ae99-126">-Property</span><span class="sxs-lookup"><span data-stu-id="2ae99-126">-Property</span></span>
<span data-ttu-id="2ae99-127">Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="2ae99-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="2ae99-128">Используйте командлет **Get-DscResource** для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="2ae99-128">Use the **Get-DscResource** cmdlet to discover resource properties and their types.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ae99-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2ae99-129">CommonParameters</span></span>
<span data-ttu-id="2ae99-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2ae99-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ae99-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2ae99-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ae99-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2ae99-132">INPUTS</span></span>

## <span data-ttu-id="2ae99-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2ae99-133">OUTPUTS</span></span>

### <span data-ttu-id="2ae99-134">Microsoft. Management. Infrastructure. CimInstance, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="2ae99-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="2ae99-135">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2ae99-135">NOTES</span></span>

## <span data-ttu-id="2ae99-136">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2ae99-136">RELATED LINKS</span></span>

[<span data-ttu-id="2ae99-137">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="2ae99-137">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="2ae99-138">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae99-138">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="2ae99-139">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="2ae99-139">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="2ae99-140">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="2ae99-140">Get-DscResource</span></span>](Get-DscResource.md)

[<span data-ttu-id="2ae99-141">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae99-141">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="2ae99-142">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="2ae99-142">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)

[<span data-ttu-id="2ae99-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae99-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="2ae99-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ae99-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
