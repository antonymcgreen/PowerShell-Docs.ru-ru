---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 4703586008d9044ae68fd7375db65f0d0a9b9980
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "93230429"
---
# <span data-ttu-id="b07f4-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="b07f4-103">Invoke-DscResource</span></span>

## <span data-ttu-id="b07f4-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b07f4-104">SYNOPSIS</span></span>
<span data-ttu-id="b07f4-105">Выполняет метод указанного ресурса настройки требуемого состояния PowerShell (DSC).</span><span class="sxs-lookup"><span data-stu-id="b07f4-105">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="b07f4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b07f4-106">SYNTAX</span></span>

```
Invoke-DscResource [[-Method] <Object>] [[-Name] <Object>] [[-Property] <Object>]
 [[-ModuleName] <Object>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="b07f4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b07f4-107">DESCRIPTION</span></span>

<span data-ttu-id="b07f4-108">Командлет `Invoke-DscResource` выполняет метод указанного ресурса Desired State Configuration (DSC) среды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b07f4-108">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="b07f4-109">Этот командлет вызывает ресурс DSC напрямую, не создавая документ конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b07f4-109">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="b07f4-110">С помощью этого командлета продукты управления конфигурацией могут управлять Windows или Linux с помощью ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="b07f4-110">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="b07f4-111">Этот командлет также позволяет отлаживать ресурсы, когда модуль DSC работает с включенной отладкой.</span><span class="sxs-lookup"><span data-stu-id="b07f4-111">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="b07f4-112">`Invoke-DscResource` — Это экспериментальная функция в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="b07f4-112">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="b07f4-113">Чтобы использовать командлет, его необходимо включить с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="b07f4-113">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="b07f4-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="b07f4-114">EXAMPLES</span></span>

### <span data-ttu-id="b07f4-115">Пример 1. вызов метода Set ресурса путем указания его обязательных свойств</span><span class="sxs-lookup"><span data-stu-id="b07f4-115">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="b07f4-116">В этом примере вызывается метод **Set** ресурса с именем **ресурс windowsprocess** и предоставляются обязательные свойства **path** и **arguments** для запуска указанного процесса Windows.</span><span class="sxs-lookup"><span data-stu-id="b07f4-116">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="b07f4-117">Пример 2. вызов метода теста ресурса для указанного модуля</span><span class="sxs-lookup"><span data-stu-id="b07f4-117">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="b07f4-118">В этом примере вызывается метод **теста** ресурса с именем **ресурс windowsprocess** , который находится в модуле с именем **PSDesiredStateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b07f4-118">This example invokes the **Test** method of a resource named **WindowsProcess** , which is in the module named **PSDesiredStateConfiguration** .</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="b07f4-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b07f4-119">PARAMETERS</span></span>

### <span data-ttu-id="b07f4-120">-Method</span><span class="sxs-lookup"><span data-stu-id="b07f4-120">-Method</span></span>

<span data-ttu-id="b07f4-121">Указывает метод ресурса, который вызывает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="b07f4-121">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="b07f4-122">Допустимые значения для этого параметра: **Get** , **Set** и **Test** .</span><span class="sxs-lookup"><span data-stu-id="b07f4-122">The acceptable values for this parameter are: **Get** , **Set** , and **Test** .</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b07f4-123">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="b07f4-123">-ModuleName</span></span>

<span data-ttu-id="b07f4-124">Указывает имя модуля, из которого этот командлет вызывает указанный ресурс.</span><span class="sxs-lookup"><span data-stu-id="b07f4-124">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b07f4-125">-Name</span><span class="sxs-lookup"><span data-stu-id="b07f4-125">-Name</span></span>

<span data-ttu-id="b07f4-126">Указывает имя запускаемого ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="b07f4-126">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b07f4-127">-Property</span><span class="sxs-lookup"><span data-stu-id="b07f4-127">-Property</span></span>

<span data-ttu-id="b07f4-128">Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="b07f4-128">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b07f4-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b07f4-129">CommonParameters</span></span>

<span data-ttu-id="b07f4-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b07f4-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b07f4-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b07f4-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b07f4-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b07f4-132">INPUTS</span></span>

## <span data-ttu-id="b07f4-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b07f4-133">OUTPUTS</span></span>

### <span data-ttu-id="b07f4-134">Microsoft. Management. Infrastructure. CimInstance, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="b07f4-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="b07f4-135">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b07f4-135">NOTES</span></span>

- <span data-ttu-id="b07f4-136">Ранее ресурсы Windows PowerShell 5,1 работали в контексте системы, если только они не указаны в контексте пользователя с помощью ключа **PsDscRunAsCredential** .</span><span class="sxs-lookup"><span data-stu-id="b07f4-136">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential** .</span></span> <span data-ttu-id="b07f4-137">В PowerShell 7,0 ресурсы выполняются в контексте пользователя, а **PsDscRunAsCredential** больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b07f4-137">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="b07f4-138">Предыдущие конфигурации, использующие этот ключ, вызовут исключение.</span><span class="sxs-lookup"><span data-stu-id="b07f4-138">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="b07f4-139">Начиная с PowerShell 7, `Invoke-DscResource` больше не поддерживает вызов ресурсов DSC WMI.</span><span class="sxs-lookup"><span data-stu-id="b07f4-139">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="b07f4-140">Сюда входят ресурсы **файл** и **журнал** в **PSDesiredStateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b07f4-140">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration** .</span></span>

## <span data-ttu-id="b07f4-141">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b07f4-141">RELATED LINKS</span></span>

[<span data-ttu-id="b07f4-142">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="b07f4-142">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="b07f4-143">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="b07f4-143">Get-DscResource</span></span>](Get-DscResource.md)
