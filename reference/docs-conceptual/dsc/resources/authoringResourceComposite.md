---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Составные ресурсы — использование конфигурации DSC как ресурса
ms.openlocfilehash: 79fe94bd5bab8fa460714e5994d2e2487f302410
ms.sourcegitcommit: 1b88c280dd0799f225242608f0cbdab485357633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75415890"
---
# <a name="composite-resources-using-a-dsc-configuration-as-a-resource"></a><span data-ttu-id="c5d9d-103">Составные ресурсы: использование конфигурации DSC как ресурса</span><span class="sxs-lookup"><span data-stu-id="c5d9d-103">Composite resources: Using a DSC configuration as a resource</span></span>

> <span data-ttu-id="c5d9d-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c5d9d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="c5d9d-105">На практике конфигурации часто становятся длинными и сложными — вызывают множество разных ресурсов и задают большое количество свойств.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-105">In real-world situations, configurations can become long and complex, calling many different resources and setting a vast number of properties.</span></span> <span data-ttu-id="c5d9d-106">Для решения этой проблемы можно использовать настройку требуемого состояния (DSC) Windows PowerShell как ресурс для других конфигураций.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-106">To help address this complexity, you can use a Windows PowerShell Desired State Configuration (DSC) configuration as a resource for other configurations.</span></span> <span data-ttu-id="c5d9d-107">Это называется составным ресурсом.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-107">This is called a composite resource.</span></span> <span data-ttu-id="c5d9d-108">Составной ресурс — это конфигурация DSC с возможностью настройки параметров.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-108">A composite resource is a DSC configuration that takes parameters.</span></span> <span data-ttu-id="c5d9d-109">Параметры конфигурации выступают как свойства ресурса.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-109">The parameters of the configuration act as the properties of the resource.</span></span> <span data-ttu-id="c5d9d-110">Конфигурация сохраняется в виде файла с расширением `.schema.psm1`.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-110">The configuration is saved as a file with a `.schema.psm1` extension.</span></span> <span data-ttu-id="c5d9d-111">Он используется вместо схемы MOF и сценария ресурса в типовом ресурсе DSC.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-111">It takes the place of both the MOF schema, and the resource script in a typical DSC resource.</span></span> <span data-ttu-id="c5d9d-112">Дополнительные сведения см. в статье [Ресурсы DSC](resources.md).</span><span class="sxs-lookup"><span data-stu-id="c5d9d-112">For more information about DSC resources, see [Windows PowerShell Desired State Configuration Resources](resources.md).</span></span>

## <a name="creating-the-composite-resource"></a><span data-ttu-id="c5d9d-113">Создание составного ресурса</span><span class="sxs-lookup"><span data-stu-id="c5d9d-113">Creating the composite resource</span></span>

<span data-ttu-id="c5d9d-114">В нашем примере создается конфигурация, которая вызывает ряд существующих ресурсов для настройки виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-114">In our example, we create a configuration that invokes a number of existing resources to configure virtual machines.</span></span> <span data-ttu-id="c5d9d-115">Вместо указания значений для настройки в блоках конфигурации она принимает параметры, которые будут использоваться в блоках конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-115">Instead of specifying the values to be set in configuration blocks, the configuration takes in parameters that are then used in the configuration blocks.</span></span>

```powershell
Configuration xVirtualMachine
{
    param
    (
        # Name of VMs
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String[]] $VMName,

        # Name of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchName,

        # Type of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchType,

        # Source Path for VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDParentPath,

        # Destination path for diff VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDPath,

        # Startup Memory for VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMStartupMemory,

        # State of the VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMState
    )

    # Import the module that defines custom resources
    Import-DscResource -Module xComputerManagement,xHyper-V

    # Install the Hyper-V role
    WindowsFeature HyperV
    {
        Ensure = "Present"
        Name = "Hyper-V"
    }

    # Create the virtual switch
    xVMSwitch $SwitchName
    {
        Ensure = "Present"
        Name = $SwitchName
        Type = $SwitchType
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check for Parent VHD file
    File ParentVHDFile
    {
        Ensure = "Present"
        DestinationPath = $VHDParentPath
        Type = "File"
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check the destination VHD folder
    File VHDFolder
    {
        Ensure = "Present"
        DestinationPath = $VHDPath
        Type = "Directory"
        DependsOn = "[File]ParentVHDFile"
    }

    # Create VM specific diff VHD
    foreach ($Name in $VMName)
    {
        xVHD "VHD$Name"
        {
            Ensure = "Present"
            Name = $Name
            Path = $VHDPath
            ParentPath = $VHDParentPath
            DependsOn = @("[WindowsFeature]HyperV",
                          "[File]VHDFolder")
        }
    }

    # Create VM using the above VHD
    foreach($Name in $VMName)
    {
        xVMHyperV "VMachine$Name"
        {
            Ensure = "Present"
            Name = $Name
            VhDPath = (Join-Path -Path $VHDPath -ChildPath $Name)
            SwitchName = $SwitchName
            StartupMemory = $VMStartupMemory
            State = $VMState
            MACAddress = $MACAddress
            WaitForIP = $true
            DependsOn = @("[WindowsFeature]HyperV",
                          "[xVHD]VHD$Name")
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="c5d9d-116">Сейчас DSC не поддерживает размещение составных ресурсов или вложенных конфигураций в составном ресурсе.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-116">DSC doesn't currently support placing composite resources or nested configurations within a composite resource.</span></span>

### <a name="saving-the-configuration-as-a-composite-resource"></a><span data-ttu-id="c5d9d-117">Сохранение конфигурации как составного ресурса</span><span class="sxs-lookup"><span data-stu-id="c5d9d-117">Saving the configuration as a composite resource</span></span>

<span data-ttu-id="c5d9d-118">Чтобы использовать параметризованную конфигурацию как ресурс DSC, сохраните ее в структуре папок, как и любой другой ресурс на базе MOF, и присвойте имя с расширением `.schema.psm1`.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-118">To use the parameterized configuration as a DSC resource, save it in a directory structure like that of any other MOF-based resource, and name it with a `.schema.psm1` extension.</span></span> <span data-ttu-id="c5d9d-119">В этом примере мы назовем файл `xVirtualMachine.schema.psm1`.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-119">For this example, we'll name the file `xVirtualMachine.schema.psm1`.</span></span> <span data-ttu-id="c5d9d-120">Кроме того, необходимо создать манифест с именем `xVirtualMachine.psd1`, содержащий указанную ниже строку.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-120">You also need to create a manifest named `xVirtualMachine.psd1` that contains the following line.</span></span>

```powershell
RootModule = 'xVirtualMachine.schema.psm1'
```

> [!NOTE]
> <span data-ttu-id="c5d9d-121">Это в дополнение к `MyDscResources.psd1`, манифесту модуля для всех ресурсов в папке `MyDscResources`.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-121">This is in addition to `MyDscResources.psd1`, the module manifest for all resources under the `MyDscResources` folder.</span></span>

<span data-ttu-id="c5d9d-122">После выполнения этих действия структура папок должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5d9d-122">When you are done, the folder structure should be as follows.</span></span>

```
$env: psmodulepath
    |- MyDscResources
        |- MyDscResources.psd1
        |- DSCResources
            |- xVirtualMachine
                |- xVirtualMachine.psd1
                |- xVirtualMachine.schema.psm1
```

<span data-ttu-id="c5d9d-123">Теперь ресурс можно обнаружить с помощью командлета `Get-DscResource`, а его свойство — с помощью того же командлета или комбинации клавиш <kbd>CTRL</kbd>+<kbd>ПРОБЕЛ</kbd>, активирующей автозаполнение в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-123">The resource is now discoverable by using the `Get-DscResource` cmdlet, and its properties are discoverable by either that cmdlet or by using <kbd>Ctrl</kbd>+<kbd>Space</kbd> autocomplete in the Windows PowerShell ISE.</span></span>

## <a name="using-the-composite-resource"></a><span data-ttu-id="c5d9d-124">Применение составного ресурса</span><span class="sxs-lookup"><span data-stu-id="c5d9d-124">Using the composite resource</span></span>

<span data-ttu-id="c5d9d-125">Теперь создадим конфигурацию, которая вызывает составной ресурс.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-125">Next we create a configuration that calls the composite resource.</span></span> <span data-ttu-id="c5d9d-126">Эта конфигурация вызывает составной ресурс xVirtualMachine для создания виртуальной машины, а затем ресурс **xComputer**, чтобы ее переименовать.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-126">This configuration calls the xVirtualMachine composite resource to create a virtual machine, and then calls the **xComputer** resource to rename it.</span></span>

```powershell
configuration RenameVM
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VM
        {
            VMName = "Test"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }

    Node "192.168.10.1"
    {
        xComputer Name
        {
            Name = "SQL01"
            DomainName = "fourthcoffee.com"
        }
    }
}
```

<span data-ttu-id="c5d9d-127">С помощью этого ресурса также можно создать несколько виртуальных машин путем передачи массива имен виртуальных машин в ресурс xVirtualMachine.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-127">You can also use this resource to create multiple VMs by passing in an array of VM names to the xVirtualMachine resource.</span></span>

```PowerShell
Configuration MultipleVms
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VMs
        {
            VMName = "IIS01", "SQL01", "SQL02"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="c5d9d-128">Поддержка PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="c5d9d-128">Supporting PsDscRunAsCredential</span></span>

> [!NOTE]
> <span data-ttu-id="c5d9d-129">**PsDscRunAsCredential** поддерживается в PowerShell 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-129">**PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="c5d9d-130">Свойство **PsDscRunAsCredential** может использоваться в блоке ресурса [конфигураций DSC](../configurations/configurations.md), чтобы указать, что ресурс должен выполняться с указанным набором учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-130">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="c5d9d-131">Дополнительные сведения см. в разделе [Запуск DSC с учетными данными пользователя](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="c5d9d-131">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="c5d9d-132">Чтобы получить доступ к пользовательскому контексту из настраиваемого ресурса, можно использовать автоматическую переменную `$PsDscContext`.</span><span class="sxs-lookup"><span data-stu-id="c5d9d-132">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="c5d9d-133">Например, следующий код пропишет пользовательский контекст, по которому выполняется ресурс, в подробный выходной поток:</span><span class="sxs-lookup"><span data-stu-id="c5d9d-133">For example, the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if ($PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="c5d9d-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5d9d-134">See Also</span></span>

### <a name="concepts"></a><span data-ttu-id="c5d9d-135">Основные понятия</span><span class="sxs-lookup"><span data-stu-id="c5d9d-135">Concepts</span></span>

- [<span data-ttu-id="c5d9d-136">Написание пользовательских ресурсов DSC с использованием MOF</span><span class="sxs-lookup"><span data-stu-id="c5d9d-136">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
- [<span data-ttu-id="c5d9d-137">Начало работы с настройкой требуемого состояния Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5d9d-137">Get Started with Windows PowerShell Desired State Configuration</span></span>](../overview/overview.md)
