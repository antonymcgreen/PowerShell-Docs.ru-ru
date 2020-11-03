---
description: Описывает, как можно использовать классы для разработки в PowerShell с помощью настройки требуемого состояния (DSC).
keywords: powershell,командлет
Locale: en-US
ms.date: 1/11/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes_and_DSC
ms.openlocfilehash: b66129aa8479013e6397c3e60798a5d2b1929f6b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232182"
---
# <a name="about-classes-and-desired-state-configuration"></a><span data-ttu-id="fe57d-104">Сведения о классах и настройке требуемого состояния</span><span class="sxs-lookup"><span data-stu-id="fe57d-104">About Classes and Desired State Configuration</span></span>

## <a name="short-description"></a><span data-ttu-id="fe57d-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="fe57d-105">Short description</span></span>

<span data-ttu-id="fe57d-106">Описывает, как можно использовать классы для разработки в PowerShell с помощью настройки требуемого состояния (DSC).</span><span class="sxs-lookup"><span data-stu-id="fe57d-106">Describes how you can use classes to develop in PowerShell with Desired State Configuration (DSC).</span></span>

## <a name="long-description"></a><span data-ttu-id="fe57d-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="fe57d-107">Long description</span></span>

<span data-ttu-id="fe57d-108">Начиная с Windows PowerShell 5,0, язык был добавлен для определения классов и других определяемых пользователем типов с помощью формального синтаксиса и семантики, аналогичные другим объектно-ориентированным языкам программирования.</span><span class="sxs-lookup"><span data-stu-id="fe57d-108">Starting in Windows PowerShell 5.0, language was added to define classes and other user-defined types, by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="fe57d-109">Цель состоит в том, чтобы позволить разработчикам и ИТ-специалистам использовать PowerShell в более широком спектре вариантов использования, упростить разработку артефактов PowerShell, таких как ресурсы DSC, и ускорить покрытие областей управления.</span><span class="sxs-lookup"><span data-stu-id="fe57d-109">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts such as DSC resources, and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="fe57d-110">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="fe57d-110">Supported scenarios</span></span>

<span data-ttu-id="fe57d-111">Поддерживаются следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="fe57d-111">The following scenarios are supported:</span></span>

- <span data-ttu-id="fe57d-112">Определите ресурсы DSC и связанные с ними типы с помощью языка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe57d-112">Define DSC resources and their associated types by using the PowerShell language.</span></span>
- <span data-ttu-id="fe57d-113">Определение пользовательских типов в PowerShell с помощью знакомых конструкций объектно-ориентированного программирования, таких как классы, свойства, методы и наследование.</span><span class="sxs-lookup"><span data-stu-id="fe57d-113">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, and inheritance.</span></span>
- <span data-ttu-id="fe57d-114">Типы отладки с помощью языка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe57d-114">Debug types by using the PowerShell language.</span></span>
- <span data-ttu-id="fe57d-115">Создавайте и обрабатывайте исключения с помощью формальных механизмов и на нужном уровне.</span><span class="sxs-lookup"><span data-stu-id="fe57d-115">Generate and handle exceptions by using formal mechanisms, and at the right level.</span></span>

## <a name="define-dsc-resources-with-classes"></a><span data-ttu-id="fe57d-116">Определение ресурсов DSC с помощью классов</span><span class="sxs-lookup"><span data-stu-id="fe57d-116">Define DSC resources with classes</span></span>

<span data-ttu-id="fe57d-117">Помимо изменений в синтаксисе основные различия между определенным классом ресурсом DSC и поставщиком ресурса DSC командлета являются следующими элементами:</span><span class="sxs-lookup"><span data-stu-id="fe57d-117">Apart from syntax changes, the major differences between a class-defined DSC resource and a cmdlet DSC resource provider are the following items:</span></span>

- <span data-ttu-id="fe57d-118">Файл формата управляющих объектов (MOF) не требуется.</span><span class="sxs-lookup"><span data-stu-id="fe57d-118">A Management Object Format (MOF) file is not required.</span></span>
- <span data-ttu-id="fe57d-119">Вложенная папка DSCResource в папке модуля не требуется.</span><span class="sxs-lookup"><span data-stu-id="fe57d-119">A DSCResource subfolder in the module folder is not required.</span></span>
- <span data-ttu-id="fe57d-120">Файл модуля PowerShell может содержать несколько классов ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="fe57d-120">A PowerShell module file can contain multiple DSC resource classes.</span></span>

## <a name="create-a-class-defined-dsc-resource-provider"></a><span data-ttu-id="fe57d-121">Создание поставщика ресурсов DSC, определяемого классом</span><span class="sxs-lookup"><span data-stu-id="fe57d-121">Create a class-defined DSC resource provider</span></span>

<span data-ttu-id="fe57d-122">В следующем примере показан поставщик ресурсов DSC, определяемый классом, который сохраняется как модуль MyDSCResource. PSM1.</span><span class="sxs-lookup"><span data-stu-id="fe57d-122">The following example is a class-defined DSC resource provider that is saved as a module, MyDSCResource.psm1.</span></span> <span data-ttu-id="fe57d-123">Необходимо всегда включать ключевое свойство в определяемый классом поставщик ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="fe57d-123">You must always include a key property in a class-defined DSC resource provider.</span></span>

```powershell
enum Ensure
{
    Absent
    Present
}

<#
    This resource manages the file in a specific path.
    [DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource
{
    <#
        This property is the fully qualified path to the file that is
        expected to be present or absent.

        The [DscProperty(Key)] attribute indicates the property is a
        key and its value uniquely identifies a resource instance.
        Defining this attribute also means the property is required
        and DSC will ensure a value is set before calling the resource.

        A DSC resource must define at least one key property.
    #>
    [DscProperty(Key)]
    [string]$Path

    <#
        This property indicates if the settings should be present or absent
        on the system. For present, the resource ensures the file pointed
        to by $Path exists. For absent, it ensures the file point to by
        $Path does not exist.

        The [DscProperty(Mandatory)] attribute indicates the property is
        required and DSC will guarantee it is set.

        If Mandatory is not specified or if it is defined as
        Mandatory=$false, the value is not guaranteed to be set when DSC
        calls the resource.  This is appropriate for optional properties.
    #>
    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    <#
        This property defines the fully qualified path to a file that will
        be placed on the system if $Ensure = Present and $Path does not
        exist.

        NOTE: This property is required because [DscProperty(Mandatory)] is
        set.
    #>
    [DscProperty(Mandatory)]
    [string] $SourcePath

    <#
        This property reports the file's create timestamp.

        [DscProperty(NotConfigurable)] attribute indicates the property is
        not configurable in DSC configuration.  Properties marked this way
        are populated by the Get() method to report additional details
        about the resource when it is present.

    #>
    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime

    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#

        This method is equivalent of the Test-TargetResource script
        function. It should return True or False, showing whether the
        resource is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
{
            return -not $present
        }
    }

    <#
        This method is equivalent of the Get-TargetResource script function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>
    [FileResource] Get()
    {
        $present = $this.TestFilePath($this.Path)

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }
        return $this
    }

    <#
        Helper method to check if the file exists and it is correct file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($item -eq $null)
        {
            $present = $false
        }
        elseif( $item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif($item.PSIsContainer)
        {
            throw "Path $($location) is a directory path."
        }
        return $present
    }

    <#
        Helper method to copy file from source to path
    #>
    [void] CopyFile()
    {
        if(-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid code
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
# This module defines a class for a DSC "FileResource" provider.

enum Ensure
{
    Absent
    Present
}

<# This resource manages the file in a specific path.
[DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource{

    <# This is a key property
        [DscResourceKey()] also means the property is required.
        It is guaranteed to be set, other properties may not
        be set if the configuration did not specify values.
    #>
    [DscResourceKey()]
    [string]$Path

    <#
        [DscResourceMandatory()] means the property is required.
        It is guaranteed to be set, other properties may not be set
        if the configuration did not specify values.
    #>
    [DscResourceMandatory()]
    [Ensure] $Ensure

    <#
        [DscResourceMandatory()] means the property is required.
    #>
    [DscResourceMandatory()]
    [string] $SourcePath

    [DscResource

    <#
        This method replaces the Set-TargetResource DSC script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = Test-Path -path $this.Path -PathType Leaf
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $this.Path"
                Remove-Item -LiteralPath $this.Path
            }
        }
    }

    <#

        This method replaces the Test-TargetResource function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>

    [bool] Test()
    {
        if(Test-Path -path $this.Path -PathType Container)
        {
            throw "Path '$this.Path' is a directory path."
        }

        $fileExists = Test-Path -path $this.Path -PathType Leaf

        if($this.ensure -eq [Ensure]::Present)
        {
            return $fileExists
        }

        return (-not $fileExists)
    }

    <#
        This method replaces the Get-TargetResource function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>

    [FileResource] Get()
    {
        $file = Get-item $this.Path
        return $this
    }

    <#
        Helper method to copy file from source to path.
        Because this resource provider run under system,
        Only the Administrators and system have full
        access to the new created directory and file
    #>
    CopyFile()
    {
        if(Test-Path -path $this.SourcePath -PathType Container)
        {
            throw "SourcePath '$this.SourcePath' is a directory path"
        }

        if( -not (Test-Path -path $this.SourcePath -PathType Leaf))
        {
            throw "SourcePath '$this.SourcePath' is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid lines
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -path $this.Path -PathType Container)
        {
            throw "Path '$this.Path' is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <a name="create-a-module-manifest"></a><span data-ttu-id="fe57d-124">Создание манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="fe57d-124">Create a module manifest</span></span>

<span data-ttu-id="fe57d-125">После создания поставщика определенных классом ресурсов DSC и его сохранения в виде модуля создайте манифест для модуля.</span><span class="sxs-lookup"><span data-stu-id="fe57d-125">After creating the class-defined DSC resource provider, and saving it as a module, create a module manifest for the module.</span></span> <span data-ttu-id="fe57d-126">Чтобы сделать ресурс на основе класса доступным для модуля DSC, необходимо добавить в файл манифеста оператор `DscResourcesToExport`, который указывает модулю, что нужно экспортировать этот ресурс.</span><span class="sxs-lookup"><span data-stu-id="fe57d-126">To make a class-based resource available to the DSC engine, you must include a `DscResourcesToExport` statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="fe57d-127">В этом примере приведенный ниже манифест модуля сохраняется как MyDscResource.psd1.</span><span class="sxs-lookup"><span data-stu-id="fe57d-127">In this example, the following module manifest is saved as MyDscResource.psd1.</span></span>

```powershell
@{

# Script module or binary module file associated with this manifest.
RootModule = 'MyDscResource.psm1'

DscResourcesToExport = 'FileResource'

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '81624038-5e71-40f8-8905-b1a87afe22d7'

# Author of this module
Author = 'Microsoft Corporation'

# Company or vendor of this module
CompanyName = 'Microsoft Corporation'

# Copyright statement for this module
Copyright = '(c) 2014 Microsoft. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

}
```

## <a name="deploy-a-dsc-resource-provider"></a><span data-ttu-id="fe57d-128">Развертывание поставщика ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="fe57d-128">Deploy a DSC resource provider</span></span>

<span data-ttu-id="fe57d-129">Разверните новый поставщик ресурсов DSC, создав папку MyDscResource в `$pshome\Modules` или `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-129">Deploy the new DSC resource provider by creating a MyDscResource folder in `$pshome\Modules` or `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="fe57d-130">Создавать вложенную папку DSCResource не нужно.</span><span class="sxs-lookup"><span data-stu-id="fe57d-130">You do not need to create a DSCResource subfolder.</span></span> <span data-ttu-id="fe57d-131">Скопируйте файлы модуля и его манифеста (MyDscResource.psm1 и MyDscResource.psd1) в папку MyDscResource.</span><span class="sxs-lookup"><span data-stu-id="fe57d-131">Copy the module and module manifest files (MyDscResource.psm1 and MyDscResource.psd1) to the MyDscResource folder.</span></span>

<span data-ttu-id="fe57d-132">С этого момента вы можете создавать и выполнять сценарий конфигурации, как и любой другой ресурс DSC.</span><span class="sxs-lookup"><span data-stu-id="fe57d-132">From this point, you create and run a configuration script as you would with any DSC resource.</span></span>

## <a name="create-a-dsc-configuration-script"></a><span data-ttu-id="fe57d-133">Создание сценария конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="fe57d-133">Create a DSC configuration script</span></span>

<span data-ttu-id="fe57d-134">Сохранив файлы класса и манифеста в структуру папок, как описано выше, вы можете создать конфигурацию, использующую новый ресурс.</span><span class="sxs-lookup"><span data-stu-id="fe57d-134">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="fe57d-135">Следующая конфигурация ссылается на модуль MyDSCResource.</span><span class="sxs-lookup"><span data-stu-id="fe57d-135">The following configuration references the MyDSCResource module.</span></span> <span data-ttu-id="fe57d-136">Сохраните конфигурацию в виде скрипта MyResource.ps1.</span><span class="sxs-lookup"><span data-stu-id="fe57d-136">Save the configuration as a script, MyResource.ps1.</span></span>

<span data-ttu-id="fe57d-137">Сведения о запуске конфигурации DSC см. в разделе [Общие сведения о настройке требуемого состояния Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers).</span><span class="sxs-lookup"><span data-stu-id="fe57d-137">For information about how to run a DSC configuration, see [Windows PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/dscforengineers).</span></span>

<span data-ttu-id="fe57d-138">Перед запуском конфигурации создайте `C:\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-138">Before you run the configuration, create `C:\test.txt`.</span></span> <span data-ttu-id="fe57d-139">Конфигурация проверяет, существует ли файл в `c:\test\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-139">The configuration checks if the file exists at `c:\test\test.txt`.</span></span> <span data-ttu-id="fe57d-140">Если файл не существует, конфигурация копирует файл из `C:\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-140">If the file does not exist, the configuration copies the file from `C:\test.txt`.</span></span>

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "C:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

<span data-ttu-id="fe57d-141">Запустите этот скрипт так же, как любой сценарий настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="fe57d-141">Run this script as you would any DSC configuration script.</span></span> <span data-ttu-id="fe57d-142">Чтобы запустить конфигурацию, в консоли PowerShell с повышенными привилегиями выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe57d-142">To start the configuration, in an elevated PowerShell console, run the following:</span></span>

`PS C:\test> .\MyResource.ps1`

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="fe57d-143">Наследование в классах PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe57d-143">Inheritance in PowerShell classes</span></span>

### <a name="declare-base-classes-for-powershell-classes"></a><span data-ttu-id="fe57d-144">Объявление базовых классов для классов PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe57d-144">Declare base classes for PowerShell classes</span></span>

<span data-ttu-id="fe57d-145">Класс PowerShell можно объявить как базовый тип для другого класса PowerShell, как показано в следующем примере, в котором **фруктов** является базовым типом для **Apple**.</span><span class="sxs-lookup"><span data-stu-id="fe57d-145">You can declare a PowerShell class as a base type for another PowerShell class, as shown in the following example, in which **fruit** is a base type for **apple**.</span></span>

```powershell
class fruit
{
    [int]sold() {return 100500}
}

class apple : fruit {}
    [apple]::new().sold() # return 100500
```

### <a name="declare-implemented-interfaces-for-powershell-classes"></a><span data-ttu-id="fe57d-146">Объявление реализованных интерфейсов для классов PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe57d-146">Declare implemented interfaces for PowerShell classes</span></span>

<span data-ttu-id="fe57d-147">Можно объявить реализованные интерфейсы после базовых типов или сразу после двоеточия ( `:` ), если не указан базовый тип.</span><span class="sxs-lookup"><span data-stu-id="fe57d-147">You can declare implemented interfaces after base types, or immediately after a colon (`:`) if there is no base type specified.</span></span> <span data-ttu-id="fe57d-148">Все имена типов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="fe57d-148">Separate all type names by using commas.</span></span> <span data-ttu-id="fe57d-149">Это похоже на синтаксис C#.</span><span class="sxs-lookup"><span data-stu-id="fe57d-149">This is similar to C# syntax.</span></span>

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableTest : test, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

### <a name="call-base-class-constructors"></a><span data-ttu-id="fe57d-150">Вызов конструкторов базового класса</span><span class="sxs-lookup"><span data-stu-id="fe57d-150">Call base class constructors</span></span>

<span data-ttu-id="fe57d-151">Чтобы вызвать конструктор базового класса из подкласса, добавьте `base` ключевое слово, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="fe57d-151">To call a base class constructor from a subclass, add the `base` keyword, as shown in the following example:</span></span>

```powershell
class A {
    [int]$a
    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

    [B]::new().a # return 103
```

<span data-ttu-id="fe57d-152">Если базовый класс имеет конструктор по умолчанию (без параметров), можно опустить вызов явного конструктора, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="fe57d-152">If a base class has a default constructor (no parameters), you can omit an explicit constructor call, as shown.</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-methods"></a><span data-ttu-id="fe57d-153">Вызов методов базового класса</span><span class="sxs-lookup"><span data-stu-id="fe57d-153">Call base class methods</span></span>

<span data-ttu-id="fe57d-154">Можно переопределить существующие методы в подклассах.</span><span class="sxs-lookup"><span data-stu-id="fe57d-154">You can override existing methods in subclasses.</span></span> <span data-ttu-id="fe57d-155">Чтобы выполнить переопределение, объявите методы с использованием того же имени и сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="fe57d-155">To do the override, declare methods by using the same name and signature.</span></span>

```powershell
class baseClass
{
    [int]days() {return 100500}
}
class childClass1 : baseClass
{
    [int]days () {return 200600}
}

    [childClass1]::new().days() # return 200600
```

<span data-ttu-id="fe57d-156">Чтобы вызвать методы базового класса из переопределенных реализаций, приведите к базовому классу `([baseclass]$this)` при вызове.</span><span class="sxs-lookup"><span data-stu-id="fe57d-156">To call base class methods from overridden implementations, cast to the base class `([baseclass]$this)` on invocation.</span></span>

```powershell
class childClass2 : baseClass
{
    [int]days()
    {
        return 3 * ([baseClass]$this).days()
    }
}

    [childClass2]::new().days() # return 301500
```

<span data-ttu-id="fe57d-157">Все методы PowerShell являются виртуальными.</span><span class="sxs-lookup"><span data-stu-id="fe57d-157">All PowerShell methods are virtual.</span></span> <span data-ttu-id="fe57d-158">Вы можете скрыть невиртуальные методы .NET в подклассе, используя тот же синтаксис, что и для переопределения: Declare Methods с тем же именем и сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="fe57d-158">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override: declare methods with same name and signature.</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```

### <a name="current-limitations-with-class-inheritance"></a><span data-ttu-id="fe57d-159">Текущие ограничения с наследованием классов</span><span class="sxs-lookup"><span data-stu-id="fe57d-159">Current limitations with class inheritance</span></span>

<span data-ttu-id="fe57d-160">Ограничение с наследованием класса заключается в отсутствии синтаксиса объявления интерфейсов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe57d-160">A limitation with class inheritance is that there is no syntax to declare interfaces in PowerShell.</span></span>

## <a name="defining-custom-types-in-powershell"></a><span data-ttu-id="fe57d-161">Определение пользовательских типов в PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe57d-161">Defining custom types in PowerShell</span></span>

<span data-ttu-id="fe57d-162">В Windows PowerShell 5,0 появился ряд языковых элементов.</span><span class="sxs-lookup"><span data-stu-id="fe57d-162">Windows PowerShell 5.0 introduced several language elements.</span></span>

### <a name="class-keyword"></a><span data-ttu-id="fe57d-163">Ключевое слово Class</span><span class="sxs-lookup"><span data-stu-id="fe57d-163">Class keyword</span></span>

<span data-ttu-id="fe57d-164">Определяет новый класс.</span><span class="sxs-lookup"><span data-stu-id="fe57d-164">Defines a new class.</span></span>
<span data-ttu-id="fe57d-165">`class`Ключевое слово является истинным .NET Framework типом.</span><span class="sxs-lookup"><span data-stu-id="fe57d-165">The `class` keyword is a true .NET Framework type.</span></span>
<span data-ttu-id="fe57d-166">Члены класса являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="fe57d-166">Class members are public.</span></span>

```powershell
class MyClass
{
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="fe57d-167">Ключевое слово Enum и перечисления</span><span class="sxs-lookup"><span data-stu-id="fe57d-167">Enum keyword and enumerations</span></span>

<span data-ttu-id="fe57d-168">`enum`Добавлена поддержка ключевого слова, что является критическим изменением.</span><span class="sxs-lookup"><span data-stu-id="fe57d-168">Support for the `enum` keyword was added and is a breaking change.</span></span> <span data-ttu-id="fe57d-169">`enum`Разделитель в настоящее время является новой строкой.</span><span class="sxs-lookup"><span data-stu-id="fe57d-169">The `enum` delimiter is currently a newline.</span></span> <span data-ttu-id="fe57d-170">Обходной путь для тех, кто уже использует, `enum` — Вставить амперсанд ( `&` ) перед словом.</span><span class="sxs-lookup"><span data-stu-id="fe57d-170">A workaround for those who are already using `enum` is to insert an ampersand (`&`) before the word.</span></span> <span data-ttu-id="fe57d-171">Текущие ограничения. невозможно определить перечислитель с точки зрения самого себя, но можно инициализировать `enum` в терминах другого `enum` , как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="fe57d-171">Current limitations: you cannot define an enumerator in terms of itself, but you can initialize `enum` in terms of another `enum`, as shown in the following example:</span></span>

<span data-ttu-id="fe57d-172">В настоящее время невозможно указать базовый тип.</span><span class="sxs-lookup"><span data-stu-id="fe57d-172">The base type cannot currently be specified.</span></span> <span data-ttu-id="fe57d-173">Базовый тип всегда имеет значение [int].</span><span class="sxs-lookup"><span data-stu-id="fe57d-173">The base type is always [int].</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="fe57d-174">Значение перечислителя должно быть константой времени анализа.</span><span class="sxs-lookup"><span data-stu-id="fe57d-174">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="fe57d-175">Значение перечислителя не может быть результатом вызванной команды.</span><span class="sxs-lookup"><span data-stu-id="fe57d-175">The enumerator value cannot be set to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="fe57d-176">`Enum` поддерживает арифметические операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="fe57d-176">`Enum` supports arithmetic operations, as shown in the following example:</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="hidden-keyword"></a><span data-ttu-id="fe57d-177">Ключевое слово Hidden</span><span class="sxs-lookup"><span data-stu-id="fe57d-177">Hidden keyword</span></span>

<span data-ttu-id="fe57d-178">`hidden`Ключевое слово, представленное в Windows PowerShell 5,0, скрывает члены класса от результатов по умолчанию `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-178">The `hidden` keyword, introduced in Windows PowerShell 5.0, hides class members from default `Get-Member` results.</span></span> <span data-ttu-id="fe57d-179">Укажите свойство Hidden, как показано в следующей строке:</span><span class="sxs-lookup"><span data-stu-id="fe57d-179">Specify the hidden property as shown in the following line:</span></span>

```powershell
hidden [type] $classmember = <value>
```

<span data-ttu-id="fe57d-180">Скрытые члены не отображаются при нажатии клавиши TAB или IntelliSense, если завершение не происходит в классе, который определяет скрытый элемент.</span><span class="sxs-lookup"><span data-stu-id="fe57d-180">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="fe57d-181">Добавлен новый атрибут **System. Management. Automation. хидденаттрибуте** , поэтому код C# может иметь ту же семантику в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe57d-181">A new attribute, **System.Management.Automation.HiddenAttribute** , was added, so that C# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="fe57d-182">Дополнительные сведения см. в разделе [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).</span><span class="sxs-lookup"><span data-stu-id="fe57d-182">For more information, see [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).</span></span>

### <a name="import-dscresource"></a><span data-ttu-id="fe57d-183">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="fe57d-183">Import-DscResource</span></span>

<span data-ttu-id="fe57d-184">Теперь `Import-DscResource` — это динамическое ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="fe57d-184">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="fe57d-185">PowerShell анализирует корневой модуль указанного модуля, выполняя поиск классов, которые содержат атрибут DscResource.</span><span class="sxs-lookup"><span data-stu-id="fe57d-185">PowerShell parses the specified module's root module, searching for classes that contain the DscResource attribute.</span></span>

### <a name="properties"></a><span data-ttu-id="fe57d-186">Свойства</span><span class="sxs-lookup"><span data-stu-id="fe57d-186">Properties</span></span>

<span data-ttu-id="fe57d-187">Новое поле, `ImplementingAssembly` Добавлено в `ModuleInfo` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-187">A new field, `ImplementingAssembly`, was added to `ModuleInfo`.</span></span> <span data-ttu-id="fe57d-188">Если скрипт определяет классы или в загруженной сборке для двоичных модулей `ImplementingAssembly` задана динамическая сборка, созданная для модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="fe57d-188">If the script defines classes, or the loaded assembly for binary modules `ImplementingAssembly` is set to the dynamic assembly created for a script module.</span></span> <span data-ttu-id="fe57d-189">Оно не задано, когда ModuleType = Manifest.</span><span class="sxs-lookup"><span data-stu-id="fe57d-189">It is not set when ModuleType = Manifest.</span></span>

<span data-ttu-id="fe57d-190">Отражение в `ImplementingAssembly` поле обнаруживает ресурсы в модуле.</span><span class="sxs-lookup"><span data-stu-id="fe57d-190">Reflection on the `ImplementingAssembly` field discovers resources in a module.</span></span> <span data-ttu-id="fe57d-191">Это означает, что можно обнаруживать ресурсы, созданные в PowerShell или в любых других управляемых языках.</span><span class="sxs-lookup"><span data-stu-id="fe57d-191">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="fe57d-192">Поля с инициализаторами.</span><span class="sxs-lookup"><span data-stu-id="fe57d-192">Fields with initializers.</span></span>

`[int] $i = 5`

<span data-ttu-id="fe57d-193">Поддерживается static и работает как атрибут, аналогично ограничениям типа, поэтому его можно указать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="fe57d-193">Static is supported and works like an attribute, similar to the type constraints, so it can be specified in any order.</span></span>

`static [int] $count = 0`

<span data-ttu-id="fe57d-194">Тип не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fe57d-194">A type is optional.</span></span>

`$s = "hello"`

<span data-ttu-id="fe57d-195">Все члены являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="fe57d-195">All members are public.</span></span> <span data-ttu-id="fe57d-196">Для свойств требуется точка с запятой или новая строка.</span><span class="sxs-lookup"><span data-stu-id="fe57d-196">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="fe57d-197">Если тип объекта не указан, свойство имеет тип **Object**.</span><span class="sxs-lookup"><span data-stu-id="fe57d-197">If no object type is specified, the property type is **Object**.</span></span>

### <a name="constructors-and-instantiation"></a><span data-ttu-id="fe57d-198">Конструкторы и создание экземпляров</span><span class="sxs-lookup"><span data-stu-id="fe57d-198">Constructors and instantiation</span></span>

<span data-ttu-id="fe57d-199">Классы PowerShell могут иметь конструкторы, имена которых совпадают с именами их классов.</span><span class="sxs-lookup"><span data-stu-id="fe57d-199">PowerShell classes can have constructors that have the same name as their class.</span></span> <span data-ttu-id="fe57d-200">Конструкторы могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="fe57d-200">Constructors can be overloaded.</span></span> <span data-ttu-id="fe57d-201">Поддерживаются статические конструкторы.</span><span class="sxs-lookup"><span data-stu-id="fe57d-201">Static constructors are supported.</span></span>
<span data-ttu-id="fe57d-202">Свойства с выражениями инициализации инициализируются перед выполнением любого кода в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="fe57d-202">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="fe57d-203">Статические свойства инициализируются до основной части статического конструктора, а свойства экземпляра инициализируются до основной части нестатического конструктора.</span><span class="sxs-lookup"><span data-stu-id="fe57d-203">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="fe57d-204">В настоящее время нет синтаксиса для вызова конструктора из другого конструктора, например синтаксиса C#: `": this()")` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-204">Currently, there is no syntax for calling a constructor from another constructor such as the C# syntax: `": this()")`.</span></span> <span data-ttu-id="fe57d-205">Обходной путь заключается в определении общего метода Init.</span><span class="sxs-lookup"><span data-stu-id="fe57d-205">The workaround is to define a common Init method.</span></span>

<span data-ttu-id="fe57d-206">Ниже приведены способы создания экземпляров классов.</span><span class="sxs-lookup"><span data-stu-id="fe57d-206">The following are ways of instantiating classes:</span></span>

- <span data-ttu-id="fe57d-207">Создание экземпляров с помощью конструктора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe57d-207">Instantiating by using the default constructor.</span></span> <span data-ttu-id="fe57d-208">Обратите внимание, что `New-Object` в этом выпуске не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fe57d-208">Note that `New-Object` is not supported in this release.</span></span>

  `$a = [MyClass]::new()`

- <span data-ttu-id="fe57d-209">Вызов конструктора с параметром.</span><span class="sxs-lookup"><span data-stu-id="fe57d-209">Calling a constructor with a parameter.</span></span>

  `$b = [MyClass]::new(42)`

- <span data-ttu-id="fe57d-210">Передача массива в конструктор с несколькими параметрами:</span><span class="sxs-lookup"><span data-stu-id="fe57d-210">Passing an array to a constructor with multiple parameters</span></span>

  `$c = [MyClass]::new(@(42,43,44), "Hello")`

<span data-ttu-id="fe57d-211">В этом выпуске имя типа видимо только лексически, то есть оно не видимо за пределами модуля или скрипта, определяющего класс.</span><span class="sxs-lookup"><span data-stu-id="fe57d-211">For this release, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="fe57d-212">Функции могут возвращать экземпляры класса, определенного в PowerShell, а экземпляры отлично работают за пределами модуля или скрипта.</span><span class="sxs-lookup"><span data-stu-id="fe57d-212">Functions can return instances of a class defined in PowerShell, and instances work well outside of the module or script.</span></span>

<span data-ttu-id="fe57d-213">`Get-Member` **Статический** параметр перечисляет конструкторы, поэтому можно просматривать перегрузки, как и любые другие методы.</span><span class="sxs-lookup"><span data-stu-id="fe57d-213">The `Get-Member` **Static** parameter lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="fe57d-214">Производительность этого синтаксиса также значительно выше по сравнению с `New-Object`.</span><span class="sxs-lookup"><span data-stu-id="fe57d-214">The performance of this syntax is also considerably faster than `New-Object`.</span></span>

<span data-ttu-id="fe57d-215">Псевдостатический метод с именем **new** работает с типами .NET, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="fe57d-215">The pseudo-static method named **new** works with .NET types, as shown in the following example.</span></span> `[hashtable]::new()`

<span data-ttu-id="fe57d-216">Теперь можно просмотреть перегрузки конструктора с помощью `Get-Member` или так, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="fe57d-216">You can now see constructor overloads with `Get-Member`, or as shown in this example:</span></span>

```powershell
[hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

### <a name="methods"></a><span data-ttu-id="fe57d-217">Методы</span><span class="sxs-lookup"><span data-stu-id="fe57d-217">Methods</span></span>

<span data-ttu-id="fe57d-218">Метод класса PowerShell реализуется как **ScriptBlock** , имеющий только конечный блок.</span><span class="sxs-lookup"><span data-stu-id="fe57d-218">A PowerShell class method is implemented as a **ScriptBlock** that has only an end block.</span></span> <span data-ttu-id="fe57d-219">Все методы являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="fe57d-219">All methods are public.</span></span> <span data-ttu-id="fe57d-220">Ниже приведен пример определения метода с именем **DoSomething**.</span><span class="sxs-lookup"><span data-stu-id="fe57d-220">The following shows an example of defining a method named **DoSomething**.</span></span>

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x)       # method syntax
    }
    private _doSomething($a) {}
}
```

### <a name="method-invocation"></a><span data-ttu-id="fe57d-221">Вызов метода</span><span class="sxs-lookup"><span data-stu-id="fe57d-221">Method invocation</span></span>

<span data-ttu-id="fe57d-222">Поддерживаются перегруженные методы.</span><span class="sxs-lookup"><span data-stu-id="fe57d-222">Overloaded methods are supported.</span></span> <span data-ttu-id="fe57d-223">Перегруженные методы именуются аналогично существующему методу, но различаются по указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="fe57d-223">Overloaded methods are named the same as an existing method but differentiated by their specified values.</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

### <a name="invocation"></a><span data-ttu-id="fe57d-224">Вызов</span><span class="sxs-lookup"><span data-stu-id="fe57d-224">Invocation</span></span>

<span data-ttu-id="fe57d-225">См. раздел [вызов метода](#method-invocation).</span><span class="sxs-lookup"><span data-stu-id="fe57d-225">See [Method invocation](#method-invocation).</span></span>

### <a name="attributes"></a><span data-ttu-id="fe57d-226">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fe57d-226">Attributes</span></span>

<span data-ttu-id="fe57d-227">Добавлены три новых атрибута: `DscResource` , `DscResourceKey` и `DscResourceMandatory` .</span><span class="sxs-lookup"><span data-stu-id="fe57d-227">Three new attributes were added: `DscResource`, `DscResourceKey`, and `DscResourceMandatory`.</span></span>

### <a name="return-types"></a><span data-ttu-id="fe57d-228">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="fe57d-228">Return types</span></span>

<span data-ttu-id="fe57d-229">Тип возвращаемого значения является контрактом.</span><span class="sxs-lookup"><span data-stu-id="fe57d-229">Return type is a contract.</span></span> <span data-ttu-id="fe57d-230">Возвращаемое значение преобразуется к ожидаемому типу.</span><span class="sxs-lookup"><span data-stu-id="fe57d-230">The return value is converted to the expected type.</span></span>
<span data-ttu-id="fe57d-231">Если тип возвращаемого значения не указан, ему присваивается значение void.</span><span class="sxs-lookup"><span data-stu-id="fe57d-231">If no return type is specified, the return type is void.</span></span> <span data-ttu-id="fe57d-232">Потоковая передача объектов и объектов не может быть записана в конвейер намеренно или случайно.</span><span class="sxs-lookup"><span data-stu-id="fe57d-232">There is no streaming of objects and objects cannot be written to the pipeline either intentionally or by accident.</span></span>

### <a name="lexical-scoping-of-variables"></a><span data-ttu-id="fe57d-233">Лексическая область переменных</span><span class="sxs-lookup"><span data-stu-id="fe57d-233">Lexical scoping of variables</span></span>

<span data-ttu-id="fe57d-234">Ниже приведен пример того, как работает лексическая область в этом выпуске.</span><span class="sxs-lookup"><span data-stu-id="fe57d-234">The following shows an example of how lexical scoping works in this release.</span></span>

```powershell
$d = 42  # Script scope

function bar
{
    $d = 0  # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d  # error, not found dynamically
        return $script:d # no error

        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="example-create-custom-classes"></a><span data-ttu-id="fe57d-235">Пример. Создание пользовательских классов</span><span class="sxs-lookup"><span data-stu-id="fe57d-235">Example: Create custom classes</span></span>

<span data-ttu-id="fe57d-236">В следующем примере создается несколько новых пользовательских классов для реализации языка динамических стилей HTML (DSL).</span><span class="sxs-lookup"><span data-stu-id="fe57d-236">The following example creates several new, custom classes to implement an HTML Dynamic Stylesheet Language (DSL).</span></span> <span data-ttu-id="fe57d-237">В примере добавляются вспомогательные функции для создания конкретных типов элементов как часть класса element, например стили и таблицы заголовков, поскольку типы не могут использоваться вне области действия модуля.</span><span class="sxs-lookup"><span data-stu-id="fe57d-237">The example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

```powershell
# Classes that define the structure of the document
#
class Html
{
    [string] $docType
    [HtmlHead] $Head
    [Element[]] $Body

    [string] Render()
    {
        $text = "<html>`n<head>`n"
        $text += $Head
        $text += "`n</head>`n<body>`n"
        $text += $Body -join "`n" # Render all of the body elements
        $text += "</body>`n</html>"
        return $text
    }
    [string] ToString() { return $this.Render() }
}

class HtmlHead
{
    $Title
    $Base
    $Link
    $Style
    $Meta
    $Script
    [string] Render() { return "<title>$Title</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($Attributes)
        {
            foreach ($attr in $Attributes.Keys)
            {
                $attributesText = " $attr=`"$($Attributes[$attr])`""
            }
        }

        return "<${tag}${attributesText}>$text</$tag>`n"
    }
    [string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#
function H1 {[Element] @{Tag = "H1"; Text = $args.foreach{$_} -join " "}}
function H2 {[Element] @{Tag = "H2"; Text = $args.foreach{$_} -join " "}}
function H3 {[Element] @{Tag = "H3"; Text = $args.foreach{$_} -join " "}}
function P  {[Element] @{Tag = "P" ; Text = $args.foreach{$_} -join " "}}
function B  {[Element] @{Tag = "B" ; Text = $args.foreach{$_} -join " "}}
function I  {[Element] @{Tag = "I" ; Text = $args.foreach{$_} -join " "}}
function HREF
{
    param (
        $Name,
        $Link
    )

    return [Element] @{
        Tag = "A"
        Attributes = @{ HREF = $link }
        Text = $name
    }
}
function Table
{
    param (
        [Parameter(Mandatory)]
        [object[]]
            $Data,
        [Parameter()]
        [string[]]
            $Properties = "*",
        [Parameter()]
        [hashtable]
            $Attributes = @{ border=2; cellpadding=2; cellspacing=2 }
    )

    $bodyText = ""
    # Add the header tags
    $bodyText +=  $Properties.foreach{TH $_}
    # Add the rows
    $bodyText += foreach ($row in $Data)
                {
                            TR (-join $Properties.Foreach{ TD ($row.$_) } )
                }

    $table = [Element] @{
                Tag = "Table"
                Attributes = $Attributes
                Text = $bodyText
            }
    $table
}
function TH  {([Element] @{Tag="TH"; Text=$args.foreach{$_} -join " "})}
function TR  {([Element] @{Tag="TR"; Text=$args.foreach{$_} -join " "})}
function TD  {([Element] @{Tag="TD"; Text=$args.foreach{$_} -join " "})}

function Style
{
    return  [Element]  @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```

## <a name="see-also"></a><span data-ttu-id="fe57d-238">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fe57d-238">See also</span></span>

[<span data-ttu-id="fe57d-239">about_Enum</span><span class="sxs-lookup"><span data-stu-id="fe57d-239">about_Enum</span></span>](../../Microsoft.PowerShell.Core/About/about_Enum.md)

[<span data-ttu-id="fe57d-240">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="fe57d-240">about_Hidden</span></span>](../../Microsoft.PowerShell.Core/About/about_hidden.md)

[<span data-ttu-id="fe57d-241">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="fe57d-241">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="fe57d-242">about_Methods</span><span class="sxs-lookup"><span data-stu-id="fe57d-242">about_Methods</span></span>](../../Microsoft.PowerShell.Core/About/about_Methods.md)

[<span data-ttu-id="fe57d-243">Создание пользовательских ресурсов настройки требуемого состояния PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe57d-243">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)

