---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Написание пользовательских ресурсов DSC с использованием классов PowerShell
ms.openlocfilehash: 34356f65bcb83153e7395a16d2a4a5cf2e507332
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71952831"
---
# <a name="writing-a-custom-dsc-resource-with-powershell-classes"></a><span data-ttu-id="388b4-103">Написание пользовательских ресурсов DSC с использованием классов PowerShell</span><span class="sxs-lookup"><span data-stu-id="388b4-103">Writing a custom DSC resource with PowerShell classes</span></span>

> <span data-ttu-id="388b4-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="388b4-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="388b4-105">С добавлением классов PowerShell в Windows PowerShell 5.0 появилась возможность определить ресурс DSC, создав отдельный класс.</span><span class="sxs-lookup"><span data-stu-id="388b4-105">With the introduction of PowerShell classes in Windows PowerShell 5.0, you can now define a DSC resource by creating a class.</span></span> <span data-ttu-id="388b4-106">Класс определяет схему и реализацию ресурса, а значит, отдельный MOF-файл создавать не нужно.</span><span class="sxs-lookup"><span data-stu-id="388b4-106">The class defines both the schema and the implementation of the resource, so there is no need to create a separate MOF file.</span></span> <span data-ttu-id="388b4-107">Кроме того, для ресурса на основе класса используется более простая структура папок, поскольку не требуется папка **DSCResources**.</span><span class="sxs-lookup"><span data-stu-id="388b4-107">The folder structure for a class-based resource is also simpler, because a **DSCResources** folder is not necessary.</span></span>

<span data-ttu-id="388b4-108">В ресурсе DSC на основе класса схема определяется как свойства класса, которые можно изменить с помощью атрибутов, указав тип свойства.</span><span class="sxs-lookup"><span data-stu-id="388b4-108">In a class-based DSC resource, the schema is defined as properties of the class which can be modified with attributes to specify the property type..</span></span> <span data-ttu-id="388b4-109">Ресурс реализуется с помощью методов **Get()** , **Set()** и **Test()** , эквивалентных функциям **Get-TargetResource**, **Set-TargetResource** и **Test-TargetResource** в ресурсе сценария.</span><span class="sxs-lookup"><span data-stu-id="388b4-109">The resource is implemented by **Get()**, **Set()**, and **Test()** methods (equivalent to the **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** functions in a script resource.</span></span>

<span data-ttu-id="388b4-110">В этом разделе мы создадим простой ресурс с именем **FileResource**, управляющий файлом по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="388b4-110">In this topic, we will create a simple resource named **FileResource** that manages a file in a specified path.</span></span>

<span data-ttu-id="388b4-111">Дополнительные сведения о ресурсах DSC см. в статье [Создание настраиваемых ресурсов для настройки требуемого состояния Windows PowerShell](authoringResource.md).</span><span class="sxs-lookup"><span data-stu-id="388b4-111">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md)</span></span>

><span data-ttu-id="388b4-112">**Примечание.** Универсальные коллекции не поддерживаются в ресурсах на основе классов.</span><span class="sxs-lookup"><span data-stu-id="388b4-112">**Note:** Generic collections are not supported in class-based resources.</span></span>

## <a name="folder-structure-for-a-class-resource"></a><span data-ttu-id="388b4-113">Структура папок для ресурса класса</span><span class="sxs-lookup"><span data-stu-id="388b4-113">Folder structure for a class resource</span></span>

<span data-ttu-id="388b4-114">Для реализации настраиваемого ресурса DSC с помощью класса PowerShell создайте указанную ниже структуру папок.</span><span class="sxs-lookup"><span data-stu-id="388b4-114">To implement a DSC custom resource with a PowerShell class, create the following folder structure.</span></span> <span data-ttu-id="388b4-115">Класс определяется в файле **MyDscResource.psm1**, а манифест модуля — в файле **MyDscResource.psd1**.</span><span class="sxs-lookup"><span data-stu-id="388b4-115">The class is defined in **MyDscResource.psm1** and the module manifest is defined in **MyDscResource.psd1**.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResource (folder)
        MyDscResource.psm1
        MyDscResource.psd1
```

## <a name="create-the-class"></a><span data-ttu-id="388b4-116">Создание класса</span><span class="sxs-lookup"><span data-stu-id="388b4-116">Create the class</span></span>

<span data-ttu-id="388b4-117">Для создания класса PowerShell необходимо ключевое слово class.</span><span class="sxs-lookup"><span data-stu-id="388b4-117">You use the class keyword to create a PowerShell class.</span></span> <span data-ttu-id="388b4-118">Чтобы указать, что класс является ресурсом DSC, используйте атрибут **DscResource()** .</span><span class="sxs-lookup"><span data-stu-id="388b4-118">To specify that a class is a DSC resource, use the **DscResource()** attribute.</span></span> <span data-ttu-id="388b4-119">Имя класса — это имя ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="388b4-119">The name of the class is the name of the DSC resource.</span></span>

```powershell
[DscResource()]
class FileResource {
}
```

### <a name="declare-properties"></a><span data-ttu-id="388b4-120">Объявление свойств</span><span class="sxs-lookup"><span data-stu-id="388b4-120">Declare properties</span></span>

<span data-ttu-id="388b4-121">Схема ресурсов DSC определяется как свойства класса.</span><span class="sxs-lookup"><span data-stu-id="388b4-121">The DSC resource schema is defined as properties of the class.</span></span> <span data-ttu-id="388b4-122">Необходимо объявить три свойства описанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="388b4-122">We declare three properties as follows.</span></span>

```powershell
[DscProperty(Key)]
[string]$Path

[DscProperty(Mandatory)]
[Ensure] $Ensure

[DscProperty(Mandatory)]
[string] $SourcePath

[DscProperty(NotConfigurable)]
[Nullable[datetime]] $CreationTime
```

<span data-ttu-id="388b4-123">Обратите внимание, что для изменения свойств используются атрибуты.</span><span class="sxs-lookup"><span data-stu-id="388b4-123">Notice that the properties are modified by attributes.</span></span> <span data-ttu-id="388b4-124">Значения атрибутов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="388b4-124">The meaning of the attributes is as follows:</span></span>

- <span data-ttu-id="388b4-125">**DscProperty(Key)** : свойство является обязательным.</span><span class="sxs-lookup"><span data-stu-id="388b4-125">**DscProperty(Key)**: The property is required.</span></span> <span data-ttu-id="388b4-126">Это свойство является ключом.</span><span class="sxs-lookup"><span data-stu-id="388b4-126">The property is a key.</span></span> <span data-ttu-id="388b4-127">Значения всех свойств, помеченных как ключи, необходимо объединять для уникальной идентификации экземпляра ресурсов в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="388b4-127">The values of all properties marked as keys must combine to uniquely identify a resource instance within a configuration.</span></span>
- <span data-ttu-id="388b4-128">**DscProperty(Mandatory)** : свойство является обязательным.</span><span class="sxs-lookup"><span data-stu-id="388b4-128">**DscProperty(Mandatory)**: The property is required.</span></span>
- <span data-ttu-id="388b4-129">**DscProperty(NotConfigurable)** : свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="388b4-129">**DscProperty(NotConfigurable)**: The property is read-only.</span></span> <span data-ttu-id="388b4-130">Свойства с таким атрибутом задаются не конфигурацией, а методом **Get()** (если они есть).</span><span class="sxs-lookup"><span data-stu-id="388b4-130">Properties marked with this attribute cannot be set by a configuration, but are populated by the **Get()** method when present.</span></span>
- <span data-ttu-id="388b4-131">**DscProperty()** : свойство доступно для настройки, но не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="388b4-131">**DscProperty()**: The property is configurable, but it is not required.</span></span>

<span data-ttu-id="388b4-132">Свойства **$Path** и **$SourcePath** представляют собой строки.</span><span class="sxs-lookup"><span data-stu-id="388b4-132">The **$Path** and **$SourcePath** properties are both strings.</span></span> <span data-ttu-id="388b4-133">**$CreationTime** — это свойство [DateTime](/dotnet/api/system.datetime).</span><span class="sxs-lookup"><span data-stu-id="388b4-133">The **$CreationTime** is a [DateTime](/dotnet/api/system.datetime) property.</span></span> <span data-ttu-id="388b4-134">Свойство **$Ensure** является перечислением и определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="388b4-134">The **$Ensure** property is an enumeration type, defined as follows.</span></span>

```powershell
enum Ensure
{
    Absent
    Present
}
```

### <a name="implementing-the-methods"></a><span data-ttu-id="388b4-135">Реализация методов</span><span class="sxs-lookup"><span data-stu-id="388b4-135">Implementing the methods</span></span>

<span data-ttu-id="388b4-136">Методы **Get()** , **Set()** и **Test()** эквивалентны функциям **Get-TargetResource**, **Set-TargetResource** и **Test-TargetResource** в ресурсе сценария.</span><span class="sxs-lookup"><span data-stu-id="388b4-136">The **Get()**, **Set()**, and **Test()** methods are analogous to the **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** functions in a script resource.</span></span>

<span data-ttu-id="388b4-137">Кроме того, этот код включает CopyFile() — вспомогательную функцию, которая копирует файл из папки **$SourcePath** в папку **$Path**.</span><span class="sxs-lookup"><span data-stu-id="388b4-137">This code also includes the CopyFile() function, a helper function that copies the file from **$SourcePath** to **$Path**.</span></span>

```powershell
    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)

        if ($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#
        This method is equivalent of the Test-TargetResource script function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if ($this.Ensure -eq [Ensure]::Present)
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
        The implementation should use the keys to find appropriate resources.
        This method returns an instance of this class with the updated key
         properties.
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
        Helper method to check if the file exists and it is file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ErrorAction Ignore

        if ($item -eq $null)
        {
            $present = $false
        }
        elseif ($item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif ($item.PSIsContainer)
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
        if (-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo] $destFileInfo = New-Object -TypeName System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            Write-Verbose -Message "Creating directory $($destFileInfo.Directory.FullName)"

            <#
                Use CreateDirectory instead of New-Item to avoid code
                to handle the non-terminating error
            #>
            [System.IO.Directory]::CreateDirectory($destFileInfo.Directory.FullName)
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $($this.SourcePath) to $($this.Path)"

        # DSC engine catches and reports any error that occurs
        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
```

### <a name="the-complete-file"></a><span data-ttu-id="388b4-138">Полный файл</span><span class="sxs-lookup"><span data-stu-id="388b4-138">The complete file</span></span>

<span data-ttu-id="388b4-139">Полный файл класса:</span><span class="sxs-lookup"><span data-stu-id="388b4-139">The complete class file follows.</span></span>

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
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#
        This method is equivalent of the Test-TargetResource script function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if ($this.Ensure -eq [Ensure]::Present)
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
        The implementation should use the keys to find appropriate resources.
        This method returns an instance of this class with the updated key
         properties.
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
        Helper method to check if the file exists and it is file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($item -eq $null)
        {
            $present = $false
        }
        elseif ($item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif ($item.PSIsContainer)
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
        if (-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo] $destFileInfo = new-object System.IO.FileInfo($this.Path)
        if (-not $destFileInfo.Directory.Exists)
        {
            Write-Verbose -Message "Creating directory $($destFileInfo.Directory.FullName)"

            <#
                Use CreateDirectory instead of New-Item to avoid code
                 to handle the non-terminating error
            #>
            [System.IO.Directory]::CreateDirectory($destFileInfo.Directory.FullName)
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $($this.SourcePath) to $($this.Path)"

        # DSC engine catches and reports any error that occurs
        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
} # This module defines a class for a DSC "FileResource" provider.
```

## <a name="create-a-manifest"></a><span data-ttu-id="388b4-140">Создание манифеста</span><span class="sxs-lookup"><span data-stu-id="388b4-140">Create a manifest</span></span>

<span data-ttu-id="388b4-141">Чтобы сделать ресурс на основе класса доступным для модуля DSC, необходимо добавить в файл манифеста оператор **DscResourcesToExport**, который указывает модулю, что нужно экспортировать этот ресурс.</span><span class="sxs-lookup"><span data-stu-id="388b4-141">To make a class-based resource available to the DSC engine, you must include a **DscResourcesToExport** statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="388b4-142">Наш манифест выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="388b4-142">Our manifest looks like this:</span></span>

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

# Minimum version of the Windows PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the Windows PowerShell host required by this module
# PowerShellHostName = ''
}
```

## <a name="test-the-resource"></a><span data-ttu-id="388b4-143">Тестирование ресурса</span><span class="sxs-lookup"><span data-stu-id="388b4-143">Test the resource</span></span>

<span data-ttu-id="388b4-144">Сохранив файлы класса и манифеста в структуру папок, как описано выше, вы можете создать конфигурацию, использующую новый ресурс.</span><span class="sxs-lookup"><span data-stu-id="388b4-144">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="388b4-145">Инструкции по запуску конфигурации DSC см. в статье [Активирование конфигураций](../pull-server/enactingConfigurations.md).</span><span class="sxs-lookup"><span data-stu-id="388b4-145">For information about how to run a DSC configuration, see [Enacting configurations](../pull-server/enactingConfigurations.md).</span></span> <span data-ttu-id="388b4-146">Следующая конфигурация будет проверять, существует ли файл `c:\test\test.txt`, и, если его нет, копировать файл из `c:\test.txt` (необходимо создать файл `c:\test.txt` перед запуском конфигурации).</span><span class="sxs-lookup"><span data-stu-id="388b4-146">The following configuration will check to see whether the file at `c:\test\test.txt` exists, and, if not, copies the file from `c:\test.txt` (you should create `c:\test.txt` before you run the configuration).</span></span>

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "c:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="388b4-147">Поддержка PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="388b4-147">Supporting PsDscRunAsCredential</span></span>

><span data-ttu-id="388b4-148">**Примечание.** **PsDscRunAsCredential** поддерживается в PowerShell 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="388b4-148">**Note:** **PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="388b4-149">Свойство **PsDscRunAsCredential** может использоваться в блоке ресурса [конфигураций DSC](../configurations/configurations.md), чтобы указать, что ресурс должен выполняться с указанным набором учетных данных.</span><span class="sxs-lookup"><span data-stu-id="388b4-149">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span>
<span data-ttu-id="388b4-150">Дополнительные сведения см. в разделе [Запуск DSC с учетными данными пользователя](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="388b4-150">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

### <a name="require-or-disallow-psdscrunascredential-for-your-resource"></a><span data-ttu-id="388b4-151">Требование параметра PsDscRunAsCredential для ресурса или его запрещение</span><span class="sxs-lookup"><span data-stu-id="388b4-151">Require or disallow PsDscRunAsCredential for your resource</span></span>

<span data-ttu-id="388b4-152">Атрибут **DscResource()** принимает необязательный параметр **RunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="388b4-152">The **DscResource()** attribute takes an optional parameter **RunAsCredential**.</span></span>
<span data-ttu-id="388b4-153">Этот параметр принимает одно из трех значений:</span><span class="sxs-lookup"><span data-stu-id="388b4-153">This parameter takes one of three values:</span></span>

- <span data-ttu-id="388b4-154">`Optional` **PsDscRunAsCredential** является необязательным для конфигураций, которые вызывают этот ресурс.</span><span class="sxs-lookup"><span data-stu-id="388b4-154">`Optional` **PsDscRunAsCredential** is optional for configurations that call this resource.</span></span> <span data-ttu-id="388b4-155">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="388b4-155">This is the default value.</span></span>
- <span data-ttu-id="388b4-156">`Mandatory` **PsDscRunAsCredential** является обязательным для конфигурации, которая вызывает этот ресурс.</span><span class="sxs-lookup"><span data-stu-id="388b4-156">`Mandatory` **PsDscRunAsCredential** must be used for any configuration that calls this resource.</span></span>
- <span data-ttu-id="388b4-157">Конфигурации `NotSupported`, которые вызывают этот ресурс, не могут использовать **PsDscRunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="388b4-157">`NotSupported` Configurations that call this resource cannot use **PsDscRunAsCredential**.</span></span>
- <span data-ttu-id="388b4-158">`Default` аналогичен `Optional`.</span><span class="sxs-lookup"><span data-stu-id="388b4-158">`Default` Same as `Optional`.</span></span>

<span data-ttu-id="388b4-159">Например, используйте следующий атрибут, чтобы указать, что настраиваемый ресурс не поддерживает использование **PsDscRunAsCredential**:</span><span class="sxs-lookup"><span data-stu-id="388b4-159">For example, use the following attribute to specify that your custom resource does not support using **PsDscRunAsCredential**:</span></span>

```powershell
[DscResource(RunAsCredential=NotSupported)]
class FileResource {
}
```

### <a name="declaring-multiple-class-resources-in-a-module"></a><span data-ttu-id="388b4-160">Объявление нескольких ресурсов класса в модуле</span><span class="sxs-lookup"><span data-stu-id="388b4-160">Declaring multiple class resources in a module</span></span>

<span data-ttu-id="388b4-161">Модуль может определять несколько ресурсов DSC на основе класса.</span><span class="sxs-lookup"><span data-stu-id="388b4-161">A module can define multiple class based DSC resources.</span></span> <span data-ttu-id="388b4-162">Структуру папок можно создать одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="388b4-162">You can create the folder structure in the following ways:</span></span>

1. <span data-ttu-id="388b4-163">Определите первый ресурс в файле <ModuleName>.psm1, а последующие ресурсы в папке **DSCResources**.</span><span class="sxs-lookup"><span data-stu-id="388b4-163">Define the first resource in the "<ModuleName>.psm1" file and subsequent resources under the **DSCResources** folder.</span></span>

   ```
   $env:ProgramFiles\WindowsPowerShell\Modules (folder)
        |- MyDscResource (folder)
           |- MyDscResource.psm1
              MyDscResource.psd1
        |- DSCResources
           |- SecondResource.psm1
   ```

2. <span data-ttu-id="388b4-164">Определите все ресурсы в папке **DSCResources**.</span><span class="sxs-lookup"><span data-stu-id="388b4-164">Define all resources under the **DSCResources** folder.</span></span>

   ```
   $env:ProgramFiles\WindowsPowerShell\Modules (folder)
        |- MyDscResource (folder)
           |- MyDscResource.psm1
              MyDscResource.psd1
        |- DSCResources
           |- FirstResource.psm1
              SecondResource.psm1
   ```

> [!NOTE]
> <span data-ttu-id="388b4-165">В приведенных выше примерах можно добавлять любые файлы PSM1 из **DSCResources** в ключ **NestedModules** в файле PSD1.</span><span class="sxs-lookup"><span data-stu-id="388b4-165">In the examples above, add any PSM1 files under the **DSCResources** to the **NestedModules** key in your PSD1 file.</span></span>

### <a name="access-the-user-context"></a><span data-ttu-id="388b4-166">Доступ к контексту пользователя</span><span class="sxs-lookup"><span data-stu-id="388b4-166">Access the user context</span></span>

<span data-ttu-id="388b4-167">Чтобы получить доступ к пользовательскому контексту из настраиваемого ресурса, можно использовать автоматическую переменную `$global:PsDscContext`.</span><span class="sxs-lookup"><span data-stu-id="388b4-167">To access the user context from within a custom resource, you can use the automatic variable `$global:PsDscContext`.</span></span>

<span data-ttu-id="388b4-168">Например, следующий код пропишет пользовательский контекст, по которому выполняется ресурс, в подробный выходной поток:</span><span class="sxs-lookup"><span data-stu-id="388b4-168">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $global:PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="388b4-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="388b4-169">See Also</span></span>

[<span data-ttu-id="388b4-170">Создание пользовательских ресурсов DSC Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="388b4-170">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)
