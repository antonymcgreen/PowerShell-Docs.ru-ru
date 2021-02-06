---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 732db5a049a68e059db6062d2f6c3f850d579adc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602496"
---
# <span data-ttu-id="59777-102">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="59777-102">Invoke-DscResource</span></span>

## <span data-ttu-id="59777-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="59777-103">SYNOPSIS</span></span>
<span data-ttu-id="59777-104">Выполняет метод указанного ресурса настройки требуемого состояния PowerShell (DSC).</span><span class="sxs-lookup"><span data-stu-id="59777-104">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="59777-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59777-105">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="59777-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="59777-106">DESCRIPTION</span></span>

<span data-ttu-id="59777-107">Командлет `Invoke-DscResource` выполняет метод указанного ресурса Desired State Configuration (DSC) среды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59777-107">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="59777-108">Этот командлет вызывает ресурс DSC напрямую, не создавая документ конфигурации.</span><span class="sxs-lookup"><span data-stu-id="59777-108">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="59777-109">С помощью этого командлета продукты управления конфигурацией могут управлять Windows или Linux с помощью ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="59777-109">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="59777-110">Этот командлет также позволяет отлаживать ресурсы, когда модуль DSC работает с включенной отладкой.</span><span class="sxs-lookup"><span data-stu-id="59777-110">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="59777-111">`Invoke-DscResource` — Это экспериментальная функция в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="59777-111">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="59777-112">Чтобы использовать командлет, его необходимо включить с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="59777-112">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="59777-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="59777-113">EXAMPLES</span></span>

### <span data-ttu-id="59777-114">Пример 1. вызов метода Set ресурса путем указания его обязательных свойств</span><span class="sxs-lookup"><span data-stu-id="59777-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="59777-115">В этом примере вызывается метод **Set** ресурса с именем **ресурс windowsprocess** и предоставляются обязательные свойства **path** и **arguments** для запуска указанного процесса Windows.</span><span class="sxs-lookup"><span data-stu-id="59777-115">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="59777-116">Пример 2. вызов метода теста ресурса для указанного модуля</span><span class="sxs-lookup"><span data-stu-id="59777-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="59777-117">В этом примере вызывается метод **теста** ресурса с именем **ресурс windowsprocess**, который находится в модуле с именем **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="59777-117">This example invokes the **Test** method of a resource named **WindowsProcess**, which is in the module named **PSDesiredStateConfiguration**.</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="59777-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="59777-118">PARAMETERS</span></span>

### <span data-ttu-id="59777-119">-Method</span><span class="sxs-lookup"><span data-stu-id="59777-119">-Method</span></span>

<span data-ttu-id="59777-120">Указывает метод ресурса, который вызывает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="59777-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="59777-121">Допустимые значения для этого параметра: **Get**, **Set** и **Test**.</span><span class="sxs-lookup"><span data-stu-id="59777-121">The acceptable values for this parameter are: **Get**, **Set**, and **Test**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59777-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="59777-122">-ModuleName</span></span>

<span data-ttu-id="59777-123">Указывает имя модуля, из которого этот командлет вызывает указанный ресурс.</span><span class="sxs-lookup"><span data-stu-id="59777-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="59777-124">-Name</span><span class="sxs-lookup"><span data-stu-id="59777-124">-Name</span></span>

<span data-ttu-id="59777-125">Указывает имя запускаемого ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="59777-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="59777-126">-Property</span><span class="sxs-lookup"><span data-stu-id="59777-126">-Property</span></span>

<span data-ttu-id="59777-127">Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="59777-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59777-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="59777-128">CommonParameters</span></span>

<span data-ttu-id="59777-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="59777-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="59777-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="59777-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="59777-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="59777-131">INPUTS</span></span>

### <span data-ttu-id="59777-132">System.String</span><span class="sxs-lookup"><span data-stu-id="59777-132">System.String</span></span>

### <span data-ttu-id="59777-133">Microsoft. PowerShell. Commands. ModuleSpecification</span><span class="sxs-lookup"><span data-stu-id="59777-133">Microsoft.PowerShell.Commands.ModuleSpecification</span></span>

## <span data-ttu-id="59777-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="59777-134">OUTPUTS</span></span>

### <span data-ttu-id="59777-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="59777-135">System.Object</span></span>

## <span data-ttu-id="59777-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="59777-136">NOTES</span></span>

- <span data-ttu-id="59777-137">Ранее ресурсы Windows PowerShell 5,1 работали в контексте системы, если только они не указаны в контексте пользователя с помощью ключа **PsDscRunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="59777-137">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential**.</span></span> <span data-ttu-id="59777-138">В PowerShell 7,0 ресурсы выполняются в контексте пользователя, а **PsDscRunAsCredential** больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="59777-138">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="59777-139">Предыдущие конфигурации, использующие этот ключ, вызовут исключение.</span><span class="sxs-lookup"><span data-stu-id="59777-139">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="59777-140">Начиная с PowerShell 7, `Invoke-DscResource` больше не поддерживает вызов ресурсов DSC WMI.</span><span class="sxs-lookup"><span data-stu-id="59777-140">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="59777-141">Сюда входят ресурсы **файл** и **журнал** в **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="59777-141">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

## <span data-ttu-id="59777-142">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="59777-142">RELATED LINKS</span></span>

[<span data-ttu-id="59777-143">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="59777-143">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="59777-144">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="59777-144">Get-DscResource</span></span>](Get-DscResource.md)
