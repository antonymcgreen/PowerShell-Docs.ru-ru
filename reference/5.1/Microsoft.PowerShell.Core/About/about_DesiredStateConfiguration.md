---
description: Краткое введение в функцию настройки требуемого состояния PowerShell (DSC).
keywords: powershell,командлет
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 2f043104c67078b98355b3e54171a8993e534837
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233109"
---
# <a name="about_desiredstateconfiguration"></a><span data-ttu-id="f3d58-104">about_DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f3d58-104">about_DesiredStateConfiguration</span></span>

## <a name="short-description"></a><span data-ttu-id="f3d58-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f3d58-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="f3d58-106">Краткое введение в функцию настройки требуемого состояния PowerShell (DSC).</span><span class="sxs-lookup"><span data-stu-id="f3d58-106">Provides a brief introduction to the PowerShell Desired State Configuration (DSC) feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="f3d58-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f3d58-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f3d58-108">DSC — это платформа управления в PowerShell, которая позволяет развертывать данные конфигурации для служб программного обеспечения и управлять ими, а также управлять средой, в которой выполняются эти службы.</span><span class="sxs-lookup"><span data-stu-id="f3d58-108">DSC is a management platform in PowerShell that enables deploying and managing configuration data for software services, and managing the environment in which these services run.</span></span>

<span data-ttu-id="f3d58-109">DSC предоставляет набор расширений языка PowerShell, новых командлетов и ресурсов, которые можно использовать для декларативного указания того, как должно быть настроено состояние программной среды.</span><span class="sxs-lookup"><span data-stu-id="f3d58-109">DSC provides a set of PowerShell language extensions, new cmdlets, and resources that you can use to declaratively specify how you want the state of your software environment to be configured.</span></span> <span data-ttu-id="f3d58-110">Кроме того, с ее помощью можно поддерживать действующие конфигурации и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="f3d58-110">It also provides a means to maintain and manage existing configurations.</span></span>

<span data-ttu-id="f3d58-111">DSC представлен в PowerShell 4,0.</span><span class="sxs-lookup"><span data-stu-id="f3d58-111">DSC is introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="f3d58-112">Подробные сведения о DSC см. в статье [Обзор настройки требуемого состояния PowerShell](/powershell/scripting/dsc/overview/overview) в библиотеке TechNet.</span><span class="sxs-lookup"><span data-stu-id="f3d58-112">For detailed information about DSC, see [PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/overview) in the TechNet Library.</span></span>

## <a name="developing-dsc-resources-with-classes"></a><span data-ttu-id="f3d58-113">РАЗРАБОТКА РЕСУРСОВ DSC С ПОМОЩЬЮ КЛАССОВ</span><span class="sxs-lookup"><span data-stu-id="f3d58-113">DEVELOPING DSC RESOURCES WITH CLASSES</span></span>

<span data-ttu-id="f3d58-114">Начиная с PowerShell 5,0 можно разрабатывать ресурсы DSC с помощью классов.</span><span class="sxs-lookup"><span data-stu-id="f3d58-114">Starting in PowerShell 5.0, you can develop DSC resources by using classes.</span></span>
<span data-ttu-id="f3d58-115">Дополнительные сведения см. в статьях [about_Classes](about_Classes.md)и [запись пользовательского ресурса DSC с помощью классов PowerShell](/previous-versions//dn948461(v=technet.10)) в Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="f3d58-115">For more information, see [about_Classes](about_Classes.md), and [Writing a custom DSC resource with PowerShell classes](/previous-versions//dn948461(v=technet.10)) on Microsoft TechNet.</span></span>

## <a name="using-dsc"></a><span data-ttu-id="f3d58-116">ИСПОЛЬЗОВАНИЕ DSC</span><span class="sxs-lookup"><span data-stu-id="f3d58-116">USING DSC</span></span>

<span data-ttu-id="f3d58-117">Чтобы использовать DSC для настройки среды, сначала определите блок сценария PowerShell с помощью ключевого слова Configuration, за которым следует идентификатор, который, в свою очередь, за которым следует пара фигурных скобок, разделяющих блок.</span><span class="sxs-lookup"><span data-stu-id="f3d58-117">To use DSC to configure your environment, first define a PowerShell script block using the Configuration keyword, followed by an identifier, which is in turn followed by the pair of curly braces delimiting the block.</span></span> <span data-ttu-id="f3d58-118">Внутри блока конфигурации можно определить блоки узлов, указывающие состояние требуемой конфигурации для каждого узла (компьютера) в среде.</span><span class="sxs-lookup"><span data-stu-id="f3d58-118">Inside the configuration block you can define node blocks that specify the desired configuration state for each node (computer) in the environment.</span></span> <span data-ttu-id="f3d58-119">Блок узла начинается с ключевого слова Node, за которым следует имя целевого компьютера, который может быть переменной.</span><span class="sxs-lookup"><span data-stu-id="f3d58-119">A node block starts with the Node keyword, followed by the name of the target computer, which can be a variable.</span></span> <span data-ttu-id="f3d58-120">После имени компьютера поступит фигурные скобки, разделяющие блок узла.</span><span class="sxs-lookup"><span data-stu-id="f3d58-120">After the computer name, come the curly braces that delimit the node block.</span></span> <span data-ttu-id="f3d58-121">Внутри блока Node можно определить блоки ресурсов для настройки определенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f3d58-121">Inside the node block, you can define resource blocks to configure specific resources.</span></span> <span data-ttu-id="f3d58-122">Блок ресурсов начинается с имени типа ресурса, за которым следует идентификатор, который необходимо указать для этого блока, за которым следуют фигурные скобки, разделяющие блок, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f3d58-122">A resource block starts with the type name of the resource, followed by the identifier you want to specify for that block, followed by the curly braces that delimit the block, as shown in the following example.</span></span>

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

<span data-ttu-id="f3d58-123">Чтобы создать конфигурацию, вызовите блок конфигурации так же, как при вызове функции PowerShell, передав все ожидаемые параметры (два в примере выше).</span><span class="sxs-lookup"><span data-stu-id="f3d58-123">To create a configuration, invoke the Configuration block the same way you would invoke a PowerShell function, passing in any expected parameters you may have defined (two in the example above).</span></span> <span data-ttu-id="f3d58-124">Например, в этом случае:</span><span class="sxs-lookup"><span data-stu-id="f3d58-124">For example, in this case:</span></span>

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

<span data-ttu-id="f3d58-125">При этом создается MOF-файл для каждого узла по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="f3d58-125">This generates a MOF file per node at the path you specify.</span></span> <span data-ttu-id="f3d58-126">Эти MOF-файлы указывают требуемую конфигурацию для каждого узла.</span><span class="sxs-lookup"><span data-stu-id="f3d58-126">These MOF files specify the desired configuration for each node.</span></span> <span data-ttu-id="f3d58-127">Затем используйте следующий командлет для анализа MOF-файлов конфигурации, отправки каждого узла соответствующей конфигурации и внедрения этих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="f3d58-127">Next, use the following cmdlet to parse the configuration MOF files, send each node its corresponding configuration, and enact those configurations.</span></span> <span data-ttu-id="f3d58-128">Обратите внимание, что вам не нужно создавать отдельный MOF-файл для ресурсов DSC на основе классов.</span><span class="sxs-lookup"><span data-stu-id="f3d58-128">Note that you do not need to create a separate MOF file for class-based DSC resources.</span></span>

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a><span data-ttu-id="f3d58-129">ИСПОЛЬЗОВАНИЕ DSC ДЛЯ ОБСЛУЖИВАНИЯ СОСТОЯНИЯ КОНФИГУРАЦИИ</span><span class="sxs-lookup"><span data-stu-id="f3d58-129">USING DSC TO MAINTAIN CONFIGURATION STATE</span></span>

<span data-ttu-id="f3d58-130">В DSC конфигурация — идемпотентными.</span><span class="sxs-lookup"><span data-stu-id="f3d58-130">With DSC, configuration is idempotent.</span></span> <span data-ttu-id="f3d58-131">Это означает, что при использовании DSC для одной и той же конфигурации несколько раз результирующее состояние конфигурации всегда будет одинаковым.</span><span class="sxs-lookup"><span data-stu-id="f3d58-131">This means that if you use DSC to enact the same configuration more than once, the resulting configuration state will always be the same.</span></span> <span data-ttu-id="f3d58-132">По этой причине, если вы подозреваете, что все узлы в вашей среде были смещены от желаемого состояния конфигурации, можно снова применить ту же конфигурацию DSC еще раз, чтобы вернуть их в нужное состояние.</span><span class="sxs-lookup"><span data-stu-id="f3d58-132">Because of this, if you suspect that any nodes in your environment may have drifted from the desired state of configuration, you can enact the same DSC configuration again to bring them back to the desired state.</span></span> <span data-ttu-id="f3d58-133">Нет необходимости изменять скрипт конфигурации для адресации только тех ресурсов, состояние которых смещено от требуемого состояния.</span><span class="sxs-lookup"><span data-stu-id="f3d58-133">You do not need to modify the configuration script to address only those resources whose state has drifted from the desired state.</span></span>

<span data-ttu-id="f3d58-134">В следующем примере показано, как проверить фактическое состояние конфигурации на данном узле, смещенное от последней конфигурации DSC, заданной на узле.</span><span class="sxs-lookup"><span data-stu-id="f3d58-134">The following example shows how you can verify whether the actual state of configuration on a given node has drifted from the last DSC configuration enacted on the node.</span></span> <span data-ttu-id="f3d58-135">В этом примере проверяется конфигурация локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="f3d58-135">In this example we are checking the configuration of the local computer.</span></span>

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a><span data-ttu-id="f3d58-136">ВСТРОЕННЫЕ РЕСУРСЫ DSC</span><span class="sxs-lookup"><span data-stu-id="f3d58-136">BUILT-IN DSC RESOURCES</span></span>

<span data-ttu-id="f3d58-137">В скриптах конфигурации можно использовать следующие встроенные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="f3d58-137">You can use the following built-in resources in your configuration scripts:</span></span>

|<span data-ttu-id="f3d58-138">name</span><span class="sxs-lookup"><span data-stu-id="f3d58-138">Name</span></span>                  |<span data-ttu-id="f3d58-139">Свойства</span><span class="sxs-lookup"><span data-stu-id="f3d58-139">Properties</span></span>                                         |
|----------------------|---------------------------------------------------|
|<span data-ttu-id="f3d58-140">Файл</span><span class="sxs-lookup"><span data-stu-id="f3d58-140">File</span></span>                  |<span data-ttu-id="f3d58-141">{DestinationPath, атрибуты, контрольная сумма, содержимое...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-141">{DestinationPath, Attributes, Checksum, Content...}</span></span>|
|<span data-ttu-id="f3d58-142">Архив</span><span class="sxs-lookup"><span data-stu-id="f3d58-142">Archive</span></span>               |<span data-ttu-id="f3d58-143">{Назначение, путь, контрольная сумма, учетные данные...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-143">{Destination, Path, Checksum, Credential...}</span></span>       |
|<span data-ttu-id="f3d58-144">Среда</span><span class="sxs-lookup"><span data-stu-id="f3d58-144">Environment</span></span>           |<span data-ttu-id="f3d58-145">{Name, DependsOn, убедитесь, что путь...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-145">{Name, DependsOn, Ensure, Path...}</span></span>                 |
|<span data-ttu-id="f3d58-146">Group</span><span class="sxs-lookup"><span data-stu-id="f3d58-146">Group</span></span>                 |<span data-ttu-id="f3d58-147">{GroupName, Credential, DependsOn, описание...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-147">{GroupName, Credential, DependsOn, Description...}</span></span> |
|<span data-ttu-id="f3d58-148">Журнал</span><span class="sxs-lookup"><span data-stu-id="f3d58-148">Log</span></span>                   |<span data-ttu-id="f3d58-149">{Message, DependsOn, PsDscRunAsCredential}</span><span class="sxs-lookup"><span data-stu-id="f3d58-149">{Message, DependsOn, PsDscRunAsCredential}</span></span>         |
|<span data-ttu-id="f3d58-150">Пакет</span><span class="sxs-lookup"><span data-stu-id="f3d58-150">Package</span></span>               |<span data-ttu-id="f3d58-151">{Name, Path, ProductId, arguments...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-151">{Name, Path, ProductId, Arguments...}</span></span>              |
|<span data-ttu-id="f3d58-152">Реестр</span><span class="sxs-lookup"><span data-stu-id="f3d58-152">Registry</span></span>              |<span data-ttu-id="f3d58-153">{Key, ValueName, DependsOn, убедитесь, что...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-153">{Key, ValueName, DependsOn, Ensure...}</span></span>             |
|<span data-ttu-id="f3d58-154">Сценарий</span><span class="sxs-lookup"><span data-stu-id="f3d58-154">Script</span></span>                |<span data-ttu-id="f3d58-155">{Надстрочный, SetScript, TestScript, Credential...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-155">{GetScript, SetScript, TestScript, Credential...}</span></span>  |
|<span data-ttu-id="f3d58-156">Служба</span><span class="sxs-lookup"><span data-stu-id="f3d58-156">Service</span></span>               |<span data-ttu-id="f3d58-157">{Name, Буилтинаккаунт, Credentials, DEPENDENCIES...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-157">{Name, BuiltInAccount, Credential, Dependencies...}</span></span>|
|<span data-ttu-id="f3d58-158">Пользователь</span><span class="sxs-lookup"><span data-stu-id="f3d58-158">User</span></span>                  |<span data-ttu-id="f3d58-159">{UserName, DependsOn, описание, отключено...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-159">{UserName, DependsOn, Description, Disabled...}</span></span>    |
|<span data-ttu-id="f3d58-160">WaitForAll</span><span class="sxs-lookup"><span data-stu-id="f3d58-160">WaitForAll</span></span>            |<span data-ttu-id="f3d58-161">{NodeName, ResourceName, DependsOn, Псдскрунаск...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-161">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="f3d58-162">WaitForAny</span><span class="sxs-lookup"><span data-stu-id="f3d58-162">WaitForAny</span></span>            |<span data-ttu-id="f3d58-163">{NodeName, ResourceName, DependsOn, Псдскрунаск...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-163">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="f3d58-164">WaitForSome</span><span class="sxs-lookup"><span data-stu-id="f3d58-164">WaitForSome</span></span>           |<span data-ttu-id="f3d58-165">{NodeCount, NodeName, ResourceName, DependsOn...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-165">{NodeCount, NodeName, ResourceName, DependsOn...}</span></span>  |
|<span data-ttu-id="f3d58-166">WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="f3d58-166">WindowsFeature</span></span>        |<span data-ttu-id="f3d58-167">{Name, Credential, DependsOn, убедитесь, что...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-167">{Name, Credential, DependsOn, Ensure...}</span></span>           |
|<span data-ttu-id="f3d58-168">WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="f3d58-168">WindowsOptionalFeature</span></span>|<span data-ttu-id="f3d58-169">{Name, DependsOn, обязательно, LogLevel...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-169">{Name, DependsOn, Ensure, LogLevel...}</span></span>             |
|<span data-ttu-id="f3d58-170">WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="f3d58-170">WindowsProcess</span></span>        |<span data-ttu-id="f3d58-171">{Аргументы, путь, учетные данные, DependsOn...}</span><span class="sxs-lookup"><span data-stu-id="f3d58-171">{Arguments, Path, Credential, DependsOn...}</span></span>        |

<span data-ttu-id="f3d58-172">Чтобы получить список доступных ресурсов DSC в системе, выполните `Get-DscResource` командлет.</span><span class="sxs-lookup"><span data-stu-id="f3d58-172">To get a list of available DSC resources on your system, run the `Get-DscResource` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="f3d58-173">В версиях PowerShell до 7.0 `Get-DscResource` не находит ресурсы DSC на основе класса.</span><span class="sxs-lookup"><span data-stu-id="f3d58-173">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="f3d58-174">В примере в этом разделе показано, как использовать ресурсы File и WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="f3d58-174">The example in this topic demonstrates how to use the File and WindowsFeature resources.</span></span> <span data-ttu-id="f3d58-175">Чтобы просмотреть все свойства, которые можно использовать с ресурсом, Вставьте курсор в ключевое слово ресурса (например, файл) в скрипте конфигурации в интегрированной среде сценариев PowerShell, удерживая нажатой <kbd>клавишу CTRL</kbd> + <kbd>пробел</kbd> .</span><span class="sxs-lookup"><span data-stu-id="f3d58-175">To see all properties that you can use with a resource, insert the cursor in the resource keyword (for example, File) within your configuration script in PowerShell ISE, hold down <kbd>CTRL</kbd>+<kbd>SPACEBAR</kbd></span></span>

## <a name="find-more-resources"></a><span data-ttu-id="f3d58-176">НАЙТИ ДОПОЛНИТЕЛЬНЫЕ РЕСУРСЫ</span><span class="sxs-lookup"><span data-stu-id="f3d58-176">FIND MORE RESOURCES</span></span>

<span data-ttu-id="f3d58-177">Вы можете скачать, установить и узнать о многих других доступных ресурсах DSC, созданных с помощью PowerShell и сообщества пользователей DSC, а также корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f3d58-177">You can download, install, and learn about many other available DSC resources that have been created by the PowerShell and DSC user community, and by Microsoft.</span></span> <span data-ttu-id="f3d58-178">Посетите [коллекция PowerShell](https://www.powershellgallery.com/) , чтобы просмотреть и узнать о доступных ресурсах DSC.</span><span class="sxs-lookup"><span data-stu-id="f3d58-178">Visit the [PowerShell Gallery](https://www.powershellgallery.com/) to browse and learn about available DSC resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3d58-179">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="f3d58-179">SEE ALSO</span></span>

[<span data-ttu-id="f3d58-180">Общие сведения о настройке требуемого состояния PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3d58-180">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="f3d58-181">Встроенные ресурсы настройки требуемого состояния PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3d58-181">Built-In PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/resources)

[<span data-ttu-id="f3d58-182">Создание пользовательских ресурсов настройки требуемого состояния PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3d58-182">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)
